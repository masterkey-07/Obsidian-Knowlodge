## Formulas
## $\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$


## Centered Formulas
## $$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$
## Greek letters : $\alpha$, $\beta$, $\omega$, $\Gamma$, $\Delta$, $\Omega$, $\epsilon$, $\varepsilon$, $\phi$,  $\varphi$.
    
5.  **Groups**. Superscripts, subscripts, and other operations apply only to the next “group”. A “group” is either a single symbol, or any formula surrounded by curly braces `{`…`}`. If you do `10^10`, you will get a surprise: 10101010. But `10^{10}` gives what you probably wanted: 10101010. Use curly braces to delimit a formula to which a superscript or subscript applies: `x^5^6` is an error; `{x^y}^z` is xyzxyz, and `x^{y^z}` is xyzxyz. Observe the differences between `x_i^2` x2ixi2, `x_{i^2}` xi2xi2 and `{x_i}^2` xi2xi2.
    
6.  **Parentheses** Ordinary symbols `()[]` make parentheses and brackets (2+3)[4+4](2+3)[4+4]. Use `\{` and `\}` for curly braces {}{}.
    
    These do _not_ scale with the formula in between, so if you write `(\frac{\sqrt x}{y^3})` the parentheses will be too small: (x√y3)(xy3). Using `\left(`…`\right)` will make the sizes adjust automatically to the formula they enclose: `\left(\frac{\sqrt x}{y^3}\right)` is (x√y3)(xy3).
    
    `\left` and`\right` apply to all the following sorts of parentheses: `(` and `)` (x)(x), `[` and `]` [x][x], `\{` and `\}` {x}{x}, `|` |x||x|, `\vert` |x||x|, `\Vert` ∥x∥‖x‖, `\langle` and `\rangle` ⟨x⟩⟨x⟩, `\lceil` and `\rceil` ⌈x⌉⌈x⌉, and `\lfloor` and `\rfloor` ⌊x⌋⌊x⌋. `\middle` can be used to add additional dividers. There are also invisible parentheses, denoted by `.`: to get
    
    x2∣∣53=52−32x2|35=52−32
    
    use `\left.x^2\right\rvert_3^5 = 5^2-3^2`.
    
7.  **Sums and integrals** `\sum` and `\int`; the subscript is the lower limit and the superscript is the upper limit, so for example `\sum_1^n` ∑n1∑1n. Don't forget `{`…`}` if the limits are more than a single symbol. For example, `\sum_{i=0}^\infty i^2` is ∑∞i=0i2∑i=0∞i2. Similarly, `\prod` ∏∏, `\int` ∫∫, `\bigcup` ⋃⋃, `\bigcap` ⋂⋂, `\iint` ∬∬, `\iiint` ∭∭, `\idotsint` ∫⋯∫∫⋯∫.
    
8.  **Fractions** There are [three ways to make these](https://math.meta.stackexchange.com/questions/12978/should-dfrac-be-edited-in). `\frac ab` applies to the next two groups, and produces abab; for more complicated numerators and denominators use `{`…`}`: `\frac{a+1}{b+1}` is a+1b+1a+1b+1. If the numerator and denominator are complicated, you may prefer `\over`, which splits up the group that it is in: `{a+1\over b+1}` is a+1b+1a+1b+1. For continued fractions, [use `\cfrac` instead of `\frac`](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference/5058#5058).
    
9.  **Fonts**
    

-   Use `\mathbb` or `\Bbb` for "blackboard bold": CHNQRZCHNQRZ.
-   Use `\mathbf` for boldface: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz.
    -   For expression based characters, use `\boldsymbol` instead: αα
-   Use `\mathit` for italics: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz.
-   Use `\pmb` for boldfaced italics: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz.
-   Use `\mathtt` for "typewriter" font: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz.
-   Use `\mathrm` for roman font: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz.
-   Use `\mathsf` for sans-serif font: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz.
-   Use `\mathcal` for "calligraphic" letters: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ (Uppercase only.)
-   Use `\mathscr` for script letters: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz
-   Use `\mathfrak` for "Fraktur" (old German style) letters: ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz.

10.  **Radical signs / roots** Use `sqrt`, which adjusts to the size of its argument: `\sqrt{x^3}` x3−−√x3; `\sqrt[3]{\frac xy}` xy−−√3xy3. For complicated expressions, consider using `{...}^{1/2}` instead.
    
11.  Some **special functions** such as "lim", "sin", "max", "ln", and so on are normally set in roman font instead of italic font. Use `\lim`, `\sin`, etc. to make these: `\sin x` sinxsin⁡x, not `sin x` sinxsinx. Use subscripts to attach a notation to `\lim`: `\lim_{x\to 0}`
    
    limx→0limx→0
    
    Nonstandard function names can be set with `\operatorname{foo}(x)` foo(x)foo⁡(x).
    
12.  There are a very large number of **special symbols and notations**, too many to list here; see the short listing [LATEXLATEX and AMSAMS-LATEXLATEX Symbols](https://pic.plover.com/MISC/symbols.pdf) prepared by Dr. Emre Sermutlu, or the exhaustive listing [The Comprehensive LATEXLATEX Symbol List](https://www.ctan.org/tex-archive/info/symbols/comprehensive/symbols-a4.pdf) by Scott Pakin. Some of the most common include:
    

-   `\lt \gt \le \ge \neq` <<, >>, ≤≤, ≥≥,≠≠. You can use `\not` to put a slash through almost anything: `\not\lt` ≮≮ but it often looks bad.
    
-   `\times \div \pm \mp` ××, ÷÷, ±±, ∓∓. `\cdot` is a centered dot: x⋅yx⋅y
    
-   `\cup \cap \setminus \subset \subseteq \subsetneq \supset \in \notin \emptyset \varnothing` ∪∪, ∩∩, ∖∖, ⊂⊂, ⊆⊆, ⊊⊊, ⊃⊃, ∈∈, ∉∉, ∅∅, ∅∅
    
-   `{n+1 \choose 2k}` or `\binom{n+1}{2k}` (n+12k)(n+12k)
    
-   $\to \gets \ \rightarrow \leftarrow \ \Rightarrow \Leftarrow \ \mapsto \implies \ \iff$
    
-   `\land \lor \lnot \forall \exists \top \bot \vdash \vDash` ∧∧, ∨∨, ¬¬, ∀∀, ∃∃, ⊤⊤, ⊥⊥, ⊢⊢, ⊨⊨
    
-   `\star \ast \oplus \circ \bullet` ⋆⋆, ∗∗, ⊕⊕, ∘∘, ∙∙
    
-   `\approx \sim \simeq \cong \equiv \prec \lhd` ≈≈, ∼∼, ≃≃, ≅≅, ≡≡, ≺≺, ⊲⊲
    
-   `\infty \aleph_0` ∞ℵ0∞ℵ0 `\nabla \partial` ∇∇, ∂∂ `\Im \Re` Iℑ, Rℜ
    
-   For modular equivalence, use `\pmod` like this: `a\equiv b\pmod n` a≡b(modn)a≡b(modn). For the binary mod operator, use `\bmod` like this: `a\bmod 17` amod17amod17.
    
-   Use `\dots` for the triple dots in a1,a2,…,ana1,a2,…,an and a1+a2+⋯+ana1+a2+⋯+an
    
-   Script lowercase l is `\ell` ℓℓ.
    
    [Detexify](https://detexify.kirelabs.org/classify.html) lets you draw a symbol on a web page and then lists the TEXTEX symbols that seem to resemble it. These are not guaranteed to work in MathJax, but it's a good place to start. To check that a command is supported, note that MathJax.org maintains a [list of currently supported LATEXLATEX commands](https://docs.mathjax.org/en/latest/input/tex/macros/index.html), and one can also check Dr. Carol JVF Burns's page of [TEXTEX Commands Available in MathJax](https://www.onemathematicalcat.org/MathJaxDocumentation/TeXSyntax.htm).
    

13.  **Spaces** MathJax usually decides for itself how to space formulas, using a complex set of rules. Putting extra literal spaces into formulas will not change the amount of space MathJax puts in: `a␣b` and `a␣␣␣␣b` are both abab. To add more space, use `\,` for a thin space abab; `\;` for a wider space abab. `\quad` and `\qquad` are large spaces: abab, abab.
    
    To set plain text, use `\text{…}`: {x∈s∣x is extra large}{x∈s∣x is extra large}. You can nest `$…$` inside of `\text{…}`, for example to access spaces.
    
14.  **Accents and diacritical marks** Use `\hat` for a single symbol x^x^, `\widehat` for a larger formula xyˆxy^. If you make it too wide, it will look silly. Similarly, there are `\bar` x¯x¯ and `\overline` xyz¯¯¯¯¯¯¯¯xyz¯, and `\vec` x⃗ x→ and `\overrightarrow` xy−→xy→ and `\overleftrightarrow` xy←→xy↔. For dots, as in ddxxx˙=x˙2+xx¨ddxxx˙=x˙2+xx¨, use `\dot` and `\ddot`.
    
15.  Special characters used for MathJax interpreting can be escaped using the `\` character: \$ $$, `\{` {{, `\}` }}, `\_` __, `\#` ##, `\&` &&. If you want `\` itself, you should use `\backslash` (symbol) or `\setminus` ([binary operation](https://tex.stackexchange.com/questions/511328/difference-between-commands-setminus-and-backslash/511332#511332)) for ∖∖, because `\\` is for a new line.