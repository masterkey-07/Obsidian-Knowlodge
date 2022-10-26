[[Relational Database]] Concept

## Description

### The Process to Divide and Create new Tables to Improve [[Data Redundancy]]

## First Normalization

Purchase Table 
| Purchase Id| Product Id | Product Name | User Id | User Name | Product Price | Product Quantity |
| --- | ---  |---  | ---  | ---  | ---  | ---  |
| 1 | 1 | PS4 | 1 | Joe | 3000 | 1 |
| 2 | 2 | PS5 | 2 | Liz | 4000 | 2 |

## Second Normalization

Purchase Table
| Purchase Id| Product Id | Product Name | User Id |  Product Price | Product Quantity |
| ---| ---| ---  | ---  | ---  | ---  |
| 1 | 1 | PS4 | 1 |  3000 | 1 |
| 2 | 2 | PS5 | 2 |  4000 | 2 |

User Table
| User Id | User Name|
| ---  |---  |
|  1 | Joe  |
|  2 | Liz  |



## Third Normalization

Purchase Table
| Purchase Id| Product Id |  User Id | Product Quantity |
| ---| ---| ---  | ---  | 
| 1 | 1 | 1 | 1 |
| 2 | 2  | 2 | 2 |

Product Table
|  Product Id | Product Name |Product Price |
| ---| ---| ---  |
| 1 | PS4  |  3000  |
 | 2 | PS5  |  4000  |

User Table
| User Id | User Name|
| ---  |---  |
|  1 | Joe  |
|  2 | Liz  |



