# Description

### Uses algebraic structures for modeling data, and defining queries.

---

# Operations

## $\sigma$ : for selection, filter per rows
## $\pi$ : for projection, filter per columns 

# Examples

1) List all data of Laptop  
> σ true Laptop

2) List models of Laptop that has $ram \ge1024$ and $HD < 250$
>π model σ ram >= 1024 and hd < 250 Laptop

3) List the PC manufacturers 
>π maker γ maker; count(maker) → counter (σ true Product ⨝ PC)

4) List the models of PC and Laptop
>π model Laptop ∪ π model PC

5) List the size of the HD that is in PC and not in Laptop
> π hd Laptop - π hd PC

6) List the Laptop manufacturers who produce models with $RAM < 1024$
>π maker γ maker; count(maker) → counter (σ Laptop.ram < 1024 Laptop ⨝ Product)

7) List PC models that have the same HD as Laptop 
>π PC.model (σ true PC ⨝ PC.hd = Laptop.hd Laptop) 

8) List models and prices of all computers (pc and laptop)
>π model, price (PC) ∪ π model, price (Laptop)  

9) List the model and type of all products and for those that are PC list the price
>π model, type, price (Product ⟕ PC)

10) List the model and speed of PCs that are priced higher than a Laptop 
>π PC.model, PC.speed σ Laptop.price ≠ null (PC ⟕ PC.price > Laptop.price Laptop)

11) List laptop models that have ram and hd greater than pcs  
>π Laptop.model σ PC.hd != null and PC.ram != null
>(Laptop ⟕ Laptop.hd > PC.hd and Laptop.ram > PC.ram PC)

