---
title: "Exclusive or"
source: "https://en.wikipedia.org/wiki/Exclusive_or"
author:
  - "Wikipedia"
published: 2002-10-16
created: 2026-07-31
description:
tags:
  - "clippings"
publish: "true"
unlisted: "true"
---
> [!danger] NOT MINE  
> This is just a reference/bookmarked article from the internet i found interesting!

---

# Exclusive or

![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Venn_0110_1001.svg/250px-Venn_0110_1001.svg.png)

Venn diagram of {\\displaystyle A\\oplus B\\oplus C}

**Exclusive or**, **exclusive disjunction**, **exclusive alternation**, **logical non-equivalence**, or [logical inequality](https://en.wikipedia.org/wiki/Logical_equality#Inequality "Logical equality") is a [logical operator](https://en.wikipedia.org/wiki/Logical_connective "Logical connective") whose negation is the [logical biconditional](https://en.wikipedia.org/wiki/Logical_biconditional "Logical biconditional"). With two inputs, XOR is true [if and only if](https://en.wikipedia.org/wiki/If_and_only_if "If and only if") the inputs differ (one is true, one is false). With multiple inputs, XOR is true if and only if the number of true inputs is [odd](https://en.wikipedia.org/wiki/Parity_\(mathematics\) "Parity (mathematics)").[^1]

It gains the name "exclusive or" because the meaning of "or" is ambiguous when both [operands](https://en.wikipedia.org/wiki/Operand "Operand") are true. XOR *excludes* that case. Some informal ways of describing XOR are "one or the other but not both", "either one or the other", and "A or B, but not A and B".

It is [symbolized](https://en.wikipedia.org/wiki/Table_of_logic_symbols "Table of logic symbols") by the prefix operator ${\displaystyle J}$ [^2]<sup><span title="Page: 16">: 16</span> </sup> and by the [infix operators](https://en.wikipedia.org/wiki/Infix_operator "Infix operator") **XOR** ([/ ˌ ɛ k s ˈ ɔː r /](https://en.wikipedia.org/wiki/Help:IPA/English "Help:IPA/English") or [/ ˈ k s ɔː r /](https://en.wikipedia.org/wiki/Help:IPA/English "Help:IPA/English")), **EOR**, **EXOR**, ${\displaystyle {\dot {\vee }}}$, ${\displaystyle {\overline {\vee }}}$, ${\displaystyle {\underline {\vee }}}$, **⩛**, ${\displaystyle \oplus }$, ${\displaystyle \nleftrightarrow }$, ${\displaystyle \not \equiv }$, and ^.

## Definition

![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8b/Variadic_logical_XOR.svg/250px-Variadic_logical_XOR.svg.png)

Each row of this binary Walsh matrix is the truth table of the variadic XOR of the arguments shown on the left. E.g. row AB corresponds to the 2-circle, and row ABC to the 3-circle Venn diagram shown above. (As in the Venn diagrams, white is false, and red is true.)

The [truth table](https://en.wikipedia.org/wiki/Truth_table "Truth table") of ${\displaystyle A\nleftrightarrow B}$ shows that it outputs true whenever the inputs differ:

| ${\displaystyle A}$ | ${\displaystyle B}$ | ${\displaystyle A\nleftrightarrow B}$ |
| --- | --- | --- |
| F | F | F |
| F | T | T |
| T | F | T |
| T | T | F |

## Equivalences, elimination, and introduction

Exclusive disjunction essentially means 'either one, but not both nor none'. In other words, the statement is true [if and only if](https://en.wikipedia.org/wiki/If_and_only_if "If and only if") one is true and the other is false. For example, if two horses are racing, then one of the two will win the race, but not both of them. The exclusive disjunction ${\displaystyle p\nleftrightarrow q}$, also denoted by ${\displaystyle p\operatorname {?} q}$ or ${\displaystyle Jpq}$, can be expressed in terms of the [logical conjunction](https://en.wikipedia.org/wiki/Logical_conjunction "Logical conjunction") ("logical and", ${\displaystyle \land }$), the [disjunction](https://en.wikipedia.org/wiki/Disjunction "Disjunction") ("logical or", ${\displaystyle \vee }$), and the [negation](https://en.wikipedia.org/wiki/Negation "Negation") (${\displaystyle \neg }$) as follows:

${\displaystyle {\begin{matrix}p\nleftrightarrow q&=&(p\vee q)\land \neg (p\land q)\end{matrix}}}$

The exclusive disjunction ${\displaystyle p\nleftrightarrow q}$ can also be expressed in the following way:

${\displaystyle {\begin{matrix}p\nleftrightarrow q&=&(p\land \lnot q)\lor (\lnot p\land q)\end{matrix}}}$

This representation of XOR may be found useful when constructing a circuit or network, because it has only one ${\displaystyle \lnot }$ operation and small number of ${\displaystyle \land }$ and ${\displaystyle \lor }$ operations. A proof of this identity is given below:

${\displaystyle {\begin{matrix}p\nleftrightarrow q&=&(p\land \lnot q)&\lor &(\lnot p\land q)\\[3pt]&=&((p\land \lnot q)\lor \lnot p)&\land &((p\land \lnot q)\lor q)\\[3pt]&=&((p\lor \lnot p)\land (\lnot q\lor \lnot p))&\land &((p\lor q)\land (\lnot q\lor q))\\[3pt]&=&(\lnot p\lor \lnot q)&\land &(p\lor q)\\[3pt]&=&\lnot (p\land q)&\land &(p\lor q)\end{matrix}}}$

It is sometimes useful to write ${\displaystyle p\nleftrightarrow q}$ in the following way:

${\displaystyle {\begin{matrix}p\nleftrightarrow q&=&\lnot ((p\land q)\lor (\lnot p\land \lnot q))\end{matrix}}}$

or:

${\displaystyle {\begin{matrix}p\nleftrightarrow q&=&(p\lor q)\land (\lnot p\lor \lnot q)\end{matrix}}}$

This equivalence can be established by applying [De Morgan's laws](https://en.wikipedia.org/wiki/De_Morgan's_laws "De Morgan's laws") twice to the fourth line of the above proof.

The exclusive or is also equivalent to the negation of a [logical biconditional](https://en.wikipedia.org/wiki/Logical_biconditional "Logical biconditional"), by the rules of material implication (a [material conditional](https://en.wikipedia.org/wiki/Material_conditional "Material conditional") is equivalent to the disjunction of the negation of its [antecedent](https://en.wikipedia.org/wiki/Antecedent_\(logic\) "Antecedent (logic)") and its consequence) and [material equivalence](https://en.wikipedia.org/wiki/If_and_only_if "If and only if").

In summary, we have, in mathematical and in engineering notation:

${\displaystyle {\begin{matrix}p\nleftrightarrow q&=&(p\land \lnot q)&\lor &(\lnot p\land q)&=&p{\overline {q}}+{\overline {p}}q\\[3pt]&=&(p\lor q)&\land &(\lnot p\lor \lnot q)&=&(p+q)({\overline {p}}+{\overline {q}})\\[3pt]&=&(p\lor q)&\land &\lnot (p\land q)&=&(p+q)({\overline {pq}})\end{matrix}}}$

## Negation of the operator

By applying the spirit of [De Morgan's laws](https://en.wikipedia.org/wiki/De_Morgan's_laws "De Morgan's laws"), we get: 
$$
{\displaystyle \neg (p\nleftrightarrow q)\equiv \neg p\nleftrightarrow q\equiv p\nleftrightarrow \neg q.}
$$

## Relation to modern algebra

Although the [operators](https://en.wikipedia.org/wiki/Operation_\(mathematics\) "Operation (mathematics)") ${\displaystyle \wedge }$ ([conjunction](https://en.wikipedia.org/wiki/Logical_conjunction "Logical conjunction")) and ${\displaystyle \lor }$ ([disjunction](https://en.wikipedia.org/wiki/Logical_disjunction "Logical disjunction")) are very useful in logic systems, they fail a more generalizable structure in the following way:

The systems ${\displaystyle (\{T,F\},\wedge )}$ and ${\displaystyle (\{T,F\},\lor )}$ are [monoids](https://en.wikipedia.org/wiki/Monoid "Monoid"), but neither is a [group](https://en.wikipedia.org/wiki/Group_\(mathematics\) "Group (mathematics)"). This unfortunately prevents the combination of these two systems into larger structures, such as a [mathematical ring](https://en.wikipedia.org/wiki/Ring_\(mathematics\) "Ring (mathematics)").

However, the system using exclusive or ${\displaystyle (\{T,F\},\oplus )}$ *is* an [abelian group](https://en.wikipedia.org/wiki/Abelian_group "Abelian group"). The combination of operators ${\displaystyle \wedge }$ and ${\displaystyle \oplus }$ over elements ${\displaystyle \{T,F\}}$ produce the well-known [two-element field ${\displaystyle \mathbb {F} _{2}}$](https://en.wikipedia.org/wiki/GF\(2\) "GF(2)"). This field can represent any logic obtainable with the system ${\displaystyle (\land ,\lor )}$ and has the added benefit of the arsenal of algebraic analysis tools for fields.

More specifically, if one associates ${\displaystyle F}$ with 0 and ${\displaystyle T}$ with 1, one can interpret the logical "AND" operation as multiplication on ${\displaystyle \mathbb {F} _{2}}$ and the "XOR" operation as addition on ${\displaystyle \mathbb {F} _{2}}$:

${\displaystyle {\begin{matrix}r=p\land q&\Leftrightarrow &r=p\cdot q{\pmod {2}}\\[3pt]r=p\oplus q&\Leftrightarrow &r=p+q{\pmod {2}}\\\end{matrix}}}$

The description of a [Boolean function](https://en.wikipedia.org/wiki/Boolean_function "Boolean function") as a [polynomial](https://en.wikipedia.org/wiki/Polynomial "Polynomial") in ${\displaystyle \mathbb {F} _{2}}$, using this basis, is called the function's [algebraic normal form](https://en.wikipedia.org/wiki/Algebraic_normal_form "Algebraic normal form").[^3]

## Exclusive or in natural language

Disjunction is often understood exclusively in [natural languages](https://en.wikipedia.org/wiki/Natural_language "Natural language"). In English, the disjunctive word "or" is often understood exclusively, particularly when used with the particle "either". The English example below would normally be understood in conversation as implying that Mary is not both a singer and a poet.[^4] [^5]

1\. Mary is a singer or a poet.

However, disjunction can also be understood inclusively, even in combination with "either". For instance, the first example below shows that "either" can be [felicitously](https://en.wikipedia.org/wiki/Felicity_\(pragmatics\) "Felicity (pragmatics)") used in combination with an outright statement that both disjuncts are true. The second example shows that the exclusive inference vanishes away under [downward entailing](https://en.wikipedia.org/wiki/Downward_entailing "Downward entailing") contexts. If disjunction were understood as exclusive in this example, it would leave open the possibility that some people ate both rice and beans.[^4]

2\. Mary is either a singer or a poet or both.

3\. Nobody ate either rice or beans.

Examples such as the above have motivated analyses of the exclusivity inference as [pragmatic](https://en.wikipedia.org/wiki/Pragmatics "Pragmatics") [conversational implicatures](https://en.wikipedia.org/wiki/Conversational_implicature "Conversational implicature") calculated on the basis of an inclusive [semantics](https://en.wikipedia.org/wiki/Formal_semantics_\(linguistics\) "Formal semantics (linguistics)"). Implicatures are typically [cancellable](https://en.wikipedia.org/wiki/Cancellable_\(linguistics\) "Cancellable (linguistics)") and do not arise in downward entailing contexts if their calculation depends on the [Maxim of Quantity](https://en.wikipedia.org/wiki/Cooperative_principle#Maxim_of_quantity_\(content_length_and_depth\) "Cooperative principle"). However, some researchers have treated exclusivity as a bona fide semantic [entailment](https://en.wikipedia.org/wiki/Entailment "Entailment") and proposed nonclassical logics which would validate it.[^4]

This behavior of English "or" is also found in other languages. However, many languages have disjunctive constructions which are robustly exclusive such as French *soit... soit*.[^4]

## Alternative symbols

The symbol used for exclusive disjunction varies from one field of application to the next, and even depends on the properties being emphasized in a given context of discussion. In addition to the abbreviation "XOR", any of the following symbols may also be seen:

- ${\displaystyle +}$ was used by [George Boole](https://en.wikipedia.org/wiki/George_Boole "George Boole") in 1847.[^6] Although Boole used ${\displaystyle +}$ mainly on classes, he also considered the case that ${\displaystyle x,y}$ are propositions in ${\displaystyle x+y}$, and at the time ${\displaystyle +}$ is a connective. Furthermore, Boole used it exclusively. Although such use does not show the relationship between inclusive disjunction (for which ${\displaystyle \vee }$ is almost fixedly used nowadays) and exclusive disjunction, and may also bring about confusions with its other uses, some classical and modern textbooks still keep such use.[^7] [^8]
- ${\displaystyle {\overline {\vee }}}$ was used by [Christine Ladd-Franklin](https://en.wikipedia.org/wiki/Christine_Ladd-Franklin "Christine Ladd-Franklin") in 1883.[^9] Strictly speaking, Ladd used ${\displaystyle A\operatorname {\overline {\vee }} B}$ to express " ${\displaystyle A}$ is-not ${\displaystyle B}$ " or "No ${\displaystyle A}$ is ${\displaystyle B}$ ", i.e., used ${\displaystyle {\overline {\vee }}}$ as exclusions, while implicitly ${\displaystyle {\overline {\vee }}}$ has the meaning of exclusive disjunction since the article is titled as "On the Algebra of Logic".
- ${\displaystyle \not =}$, denoting the negation of [equivalence](https://en.wikipedia.org/wiki/Logical_biconditional "Logical biconditional"), was used by [Ernst Schröder](https://en.wikipedia.org/wiki/Ernst_Schr%C3%B6der_\(mathematician\) "Ernst Schröder (mathematician)") in 1890,[^10]<sup><span title="Page: 307">: 307</span> </sup> Although the usage of ${\displaystyle =}$ as equivalence could be dated back to [George Boole](https://en.wikipedia.org/wiki/George_Boole "George Boole") in 1847,[^6] during the 40 years after Boole, his followers, such as [Charles Sanders Peirce](https://en.wikipedia.org/wiki/Charles_Sanders_Peirce "Charles Sanders Peirce"), [Hugh MacColl](https://en.wikipedia.org/wiki/Hugh_MacColl "Hugh MacColl"), [Giuseppe Peano](https://en.wikipedia.org/wiki/Giuseppe_Peano "Giuseppe Peano") and so on, did not use ${\displaystyle \not =}$ as non-equivalence literally which is possibly because it could be defined from negation and equivalence easily.
- ${\displaystyle \circ }$ was used by [Giuseppe Peano](https://en.wikipedia.org/wiki/Giuseppe_Peano "Giuseppe Peano") in 1894: " ${\displaystyle a\circ b=a-b\,\cup \,b-a}$. The sign ${\displaystyle \circ }$ corresponds to Latin *aut*; the sign ${\displaystyle \cup }$ to *vel*." [^11]<sup><span title="Page: 10">: 10</span> </sup> Note that the Latin word "aut" means "exclusive or" and "vel" means "inclusive or", and that Peano use ${\displaystyle \cup }$ as inclusive disjunction.
- ${\displaystyle \vee \vee }$ was used by Izrail Solomonovich Gradshtein (Израиль Соломонович Градштейн) in 1936.[^12]<sup><span title="Page: 76">: 76</span></sup>
- ${\displaystyle \oplus }$ was used by [Claude Shannon](https://en.wikipedia.org/wiki/Claude_Shannon "Claude Shannon") in 1938.[^13] Shannon borrowed the symbol as exclusive disjunction from [Edward Vermilye Huntington](https://en.wikipedia.org/wiki/Edward_Vermilye_Huntington "Edward Vermilye Huntington") in 1904.[^14] Huntington borrowed the symbol from [Gottfried Wilhelm Leibniz](https://en.wikipedia.org/wiki/Gottfried_Wilhelm_Leibniz "Gottfried Wilhelm Leibniz") in 1890 (the original date is not definitely known, but almost certainly it is written after 1685; and 1890 is the publishing time).[^15] While both Huntington in 1904 and Leibniz in 1890 used the symbol as an algebraic operation. Furthermore, Huntington in 1904 used the symbol as inclusive disjunction (logical sum) too, and in 1933 used ${\displaystyle +}$ as inclusive disjunction.[^16]
- ${\displaystyle \not \equiv }$, also denoting the negation of [equivalence](https://en.wikipedia.org/wiki/Logical_biconditional "Logical biconditional"), was used by [Alonzo Church](https://en.wikipedia.org/wiki/Alonzo_Church "Alonzo Church") in 1944.[^17]
- ${\displaystyle J}$ (as a [prefix operator](https://en.wikipedia.org/wiki/Polish_notation "Polish notation"), ${\displaystyle J\phi \psi }$) was used by [Józef Maria Bocheński](https://en.wikipedia.org/wiki/J%C3%B3zef_Maria_Boche%C5%84ski "Józef Maria Bocheński") in 1949.[^2]<sup><span title="Page: 16">: 16</span> </sup> Somebody [^18] may mistake that it is [Jan Łukasiewicz](https://en.wikipedia.org/wiki/Jan_%C5%81ukasiewicz "Jan Łukasiewicz") who is the first to use ${\displaystyle J}$ for exclusive disjunction (it seems that the mistake spreads widely), while neither in 1929 [^19] nor in other works did Łukasiewicz make such use. In fact, in 1949 Bocheński introduced a system of [Polish notation](https://en.wikipedia.org/wiki/Polish_notation "Polish notation") that names all 16 binary [connectives](https://en.wikipedia.org/wiki/Logical_connective "Logical connective") of classical logic which is a compatible extension of the notation of Łukasiewicz in 1929, and in which ${\displaystyle J}$ for exclusive disjunction appeared at the first time. Bocheński's usage of ${\displaystyle J}$ as exclusive disjunction has no relationship with the Polish "alternatywa rozłączna" of "exclusive or" and is an accident for which see the table on page 16 of the book in 1949.
- ^, the [caret](https://en.wikipedia.org/wiki/Caret "Caret"), has been used in several [programming languages](https://en.wikipedia.org/wiki/Programming_language "Programming language") to denote the [bitwise](https://en.wikipedia.org/wiki/Bitwise_operation "Bitwise operation") exclusive or operator, beginning with [C](https://en.wikipedia.org/wiki/C_\(programming_language\) "C (programming language)") [^20] and also including [C++](https://en.wikipedia.org/wiki/C++ "C++"), [C#](https://en.wikipedia.org/wiki/C_Sharp_\(programming_language\) "C Sharp (programming language)"), [D](https://en.wikipedia.org/wiki/D_\(programming_language\) "D (programming language)"), [Java](https://en.wikipedia.org/wiki/Java_\(programming_language\) "Java (programming language)"), [Perl](https://en.wikipedia.org/wiki/Perl "Perl"), [Ruby](https://en.wikipedia.org/wiki/Ruby_\(programming_language\) "Ruby (programming language)"), [PHP](https://en.wikipedia.org/wiki/PHP "PHP"), [Python](https://en.wikipedia.org/wiki/Python_\(programming_language\) "Python (programming language)") and [Rust](https://en.wikipedia.org/wiki/Rust_\(programming_language\) "Rust (programming language)").
- The [symmetric difference](https://en.wikipedia.org/wiki/Symmetric_difference "Symmetric difference") of two sets ${\displaystyle S}$ and ${\displaystyle T}$, which may be interpreted as their elementwise exclusive or, has variously been denoted as ${\displaystyle S\ominus T}$, ${\displaystyle S\mathop {\triangledown } T}$, or ${\displaystyle S\mathop {\vartriangle } T}$.[^21]

## Properties

[Commutativity](https://en.wikipedia.org/wiki/Commutative_property "Commutative property"): yes

| ${\displaystyle A\oplus B}$ | ${\displaystyle \Leftrightarrow }$ | ${\displaystyle B\oplus A}$ |
| --- | --- | --- |
| ![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/60px-Venn0110.svg.png) | ${\displaystyle \Leftrightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/60px-Venn0110.svg.png) |

[Associativity](https://en.wikipedia.org/wiki/Associative_property "Associative property"): yes

| ${\displaystyle ~A}$ | ${\displaystyle ~~~\oplus ~~~}$ | ${\displaystyle (B\oplus C)}$ | ${\displaystyle \Leftrightarrow }$ |  |  | ${\displaystyle (A\oplus B)}$ | ${\displaystyle ~~~\oplus ~~~}$ | ${\displaystyle ~C}$ |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/85/Venn_0101_0101.svg/60px-Venn_0101_0101.svg.png) | ${\displaystyle ~~~\oplus ~~~}$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Venn_0011_1100.svg/60px-Venn_0011_1100.svg.png) | ${\displaystyle \Leftrightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Venn_0110_1001.svg/60px-Venn_0110_1001.svg.png) | ${\displaystyle \Leftrightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/Venn_0110_0110.svg/60px-Venn_0110_0110.svg.png) | ${\displaystyle ~~~\oplus ~~~}$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Venn_0000_1111.svg/60px-Venn_0000_1111.svg.png) |

[Distributivity](https://en.wikipedia.org/wiki/Distributive_property "Distributive property"):

The exclusive or does not distribute over any binary function (not even itself), but [logical conjunction distributes over exclusive or](https://en.wikipedia.org/wiki/Logical_conjunction#Properties "Logical conjunction"). ${\displaystyle C\land (A\oplus B)=(C\land A)\oplus (C\land B)}$ (Conjunction and exclusive or form the multiplication and addition operations of a [field](https://en.wikipedia.org/wiki/Field_\(mathematics\) "Field (mathematics)") [GF(2)](https://en.wikipedia.org/wiki/GF\(2\) "GF(2)"), and as in any field they obey the distributive law.)

[Idempotency](https://en.wikipedia.org/wiki/Idempotence "Idempotence"): no

| ${\displaystyle ~A~}$ | ${\displaystyle ~\oplus ~}$ | ${\displaystyle ~A~}$ | ${\displaystyle \Leftrightarrow }$ | ${\displaystyle ~0~}$ | ${\displaystyle \nLeftrightarrow }$ | ${\displaystyle ~A~}$ |
| --- | --- | --- | --- | --- | --- | --- |
| ![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Venn01.svg/40px-Venn01.svg.png) | ${\displaystyle ~\oplus ~}$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Venn01.svg/40px-Venn01.svg.png) | ${\displaystyle \Leftrightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/Venn00.svg/40px-Venn00.svg.png) | ${\displaystyle \nLeftrightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Venn01.svg/40px-Venn01.svg.png) |

[Monotonicity](https://en.wikipedia.org/wiki/Monotone_Boolean_function "Monotone Boolean function"): no

| ${\displaystyle A\rightarrow B}$ | ${\displaystyle \nRightarrow }$ |  |  | ${\displaystyle (A\oplus C)}$ | ${\displaystyle \rightarrow }$ | ${\displaystyle (B\oplus C)}$ |
| --- | --- | --- | --- | --- | --- | --- |
| ![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/Venn_1011_1011.svg/60px-Venn_1011_1011.svg.png) | ${\displaystyle \nRightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/Venn_1011_1101.svg/60px-Venn_1011_1101.svg.png) | ${\displaystyle \Leftrightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a9/Venn_0101_1010.svg/60px-Venn_0101_1010.svg.png) | ${\displaystyle \rightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Venn_0011_1100.svg/60px-Venn_0011_1100.svg.png) |

Truth-preserving: no

When all inputs are true, the output is not true.

| ${\displaystyle A\land B}$ | ${\displaystyle \nRightarrow }$ | ${\displaystyle A\oplus B}$ |
| --- | --- | --- |
| ![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Venn0001.svg/60px-Venn0001.svg.png) | ${\displaystyle \nRightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/60px-Venn0110.svg.png) |

Falsehood-preserving: yes

When all inputs are false, the output is false.

| ${\displaystyle A\oplus B}$ | ${\displaystyle \Rightarrow }$ | ${\displaystyle A\lor B}$ |
| --- | --- | --- |
| ![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/60px-Venn0110.svg.png) | ${\displaystyle \Rightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/Venn0111.svg/60px-Venn0111.svg.png) |

[Walsh spectrum](https://en.wikipedia.org/wiki/Hadamard_transform "Hadamard transform"): (2,0,0,−2)

Non- [linearity](https://en.wikipedia.org/wiki/Linear#Boolean_functions "Linear"): 0

The function is linear.

Involution:

Exclusive or with one specified input, as a function of the other input, is an [involution](https://en.wikipedia.org/wiki/Involution_\(mathematics\) "Involution (mathematics)") or self-inverse function; applying it twice leaves the variable input unchanged.

| ${\displaystyle ~A\oplus B~}$ | ${\displaystyle ~\oplus ~}$ | ${\displaystyle ~B~}$ | ${\displaystyle \Leftrightarrow }$ | ${\displaystyle ~A~}$ |
| --- | --- | --- | --- | --- |
| ![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Venn0110.svg/60px-Venn0110.svg.png) | ${\displaystyle ~\oplus ~}$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/7/76/Venn0011.svg/60px-Venn0011.svg.png) | ${\displaystyle \Leftrightarrow }$ | ![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/10/Venn0101.svg/60px-Venn0101.svg.png) |

If using [binary](https://en.wikipedia.org/wiki/Binary_numeral_system "Binary numeral system") values for true (1) and false (0), then *exclusive or* works exactly like [addition](https://en.wikipedia.org/wiki/Addition "Addition") [modulo](https://en.wikipedia.org/wiki/Modular_arithmetic "Modular arithmetic") 2.

## Computer science

![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/XOR_ANSI_Labelled.svg/120px-XOR_ANSI_Labelled.svg.png)

Traditional symbolic representation of an XOR logic gate

### Bitwise operation

![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d6/Z2%5E4%3B_Cayley_table%3B_binary.svg/250px-Z2%5E4%3B_Cayley_table%3B_binary.svg.png)

Nimber addition is the exclusive or of nonnegative integers in binary representation. This is also the vector addition in {\\displaystyle (\\mathbb {Z} /2\\mathbb {Z} )^{4}}.

Exclusive disjunction is often used for bitwise operations. Examples:

- 1 XOR 1 = 0
- 1 XOR 0 = 1
- 0 XOR 1 = 1
- 0 XOR 0 = 0
- 11102 XOR 10012 = 01112 (this is equivalent to addition without [carry](https://en.wikipedia.org/wiki/Carry_\(arithmetic\) "Carry (arithmetic)"))

As noted above, since exclusive disjunction is identical to addition modulo 2, the bitwise exclusive disjunction of two *n* -bit strings is identical to the standard vector of addition in the [vector space](https://en.wikipedia.org/wiki/Vector_space "Vector space") ${\displaystyle (\mathbb {Z} /2\mathbb {Z} )^{n}}$.

In computer science, exclusive disjunction has several uses:

- It tells whether two bits are unequal.
- It is a controllable bit-flipper (the control input chooses whether or not to invert the data input).
- It tells whether there is an [odd](https://en.wikipedia.org/wiki/Parity_\(mathematics\) "Parity (mathematics)") number of 1 bits (${\displaystyle A\oplus B\oplus C\oplus D\oplus E}$ is true [if and only if](https://en.wikipedia.org/wiki/If_and_only_if "If and only if") an odd number of the variables are true), which is equal to the [parity bit](https://en.wikipedia.org/wiki/Parity_bit "Parity bit") returned by a [parity function](https://en.wikipedia.org/wiki/Parity_function "Parity function").

In logical circuits, a simple [adder](https://en.wikipedia.org/wiki/Adder_\(electronics\) "Adder (electronics)") can be made with an [XOR gate](https://en.wikipedia.org/wiki/XOR_gate "XOR gate") to add the numbers, and a series of AND, OR and NOT gates to create the carry output.

On some computer architectures, it is more efficient to store a zero in a register by XOR-ing the register with itself (bits XOR-ed with themselves are always zero) than to load and store the value zero.

In [cryptography](https://en.wikipedia.org/wiki/Cryptography "Cryptography"), XOR is sometimes used as a simple, self-inverse mixing function, such as in [one-time pad](https://en.wikipedia.org/wiki/One-time_pad "One-time pad") or [Feistel network](https://en.wikipedia.org/wiki/Feistel_cipher "Feistel cipher") systems. XOR is also heavily used in block ciphers such as AES (Rijndael) or Serpent and in block cipher implementation (CBC, CFB, OFB or CTR).

In simple threshold-activated [artificial neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network "Artificial neural network"), modeling the XOR function requires a second layer because XOR is not a [linearly separable](https://en.wikipedia.org/wiki/Linear_separability "Linear separability") function.

Similarly, XOR can be used in generating [entropy pools](https://en.wikipedia.org/wiki/Entropy_pool "Entropy pool") for [hardware random number generators](https://en.wikipedia.org/wiki/Hardware_random_number_generator "Hardware random number generator"). The XOR operation preserves randomness, meaning that a random bit XORed with a non-random bit will result in a random bit. Multiple sources of potentially random data can be combined using XOR, and the unpredictability of the output is guaranteed to be at least as good as the best individual source.[^22]

XOR is used in [RAID](https://en.wikipedia.org/wiki/RAID "RAID") 3–6 for creating parity information. For example, RAID can "back up" bytes 100111002 and 011011002 from two (or more) hard drives by XORing the just mentioned bytes, resulting in (111100002) and writing it to another drive. Under this method, if any one of the three hard drives are lost, the lost byte can be re-created by XORing bytes from the remaining drives. For instance, if the drive containing 011011002 is lost, 100111002 and 111100002 can be XORed to recover the lost byte.[^23]

XOR is also used to detect an overflow in the result of a signed binary arithmetic operation. If the leftmost retained bit of the result is not the same as the infinite number of digits to the left, then that means overflow occurred. XORing those two bits will give a "1" if there is an overflow.

XOR can be used to swap two numeric variables in computers, using the [XOR swap algorithm](https://en.wikipedia.org/wiki/XOR_swap_algorithm "XOR swap algorithm"); however this is regarded as more of a curiosity and not encouraged in practice.

[XOR linked lists](https://en.wikipedia.org/wiki/XOR_linked_list "XOR linked list") leverage XOR properties in order to save space to represent [doubly linked list](https://en.wikipedia.org/wiki/Doubly_linked_list "Doubly linked list") data structures.

In [computer graphics](https://en.wikipedia.org/wiki/Computer_graphics "Computer graphics"), XOR-based drawing methods are often used to manage such items as [bounding boxes](https://en.wikipedia.org/wiki/Bounding_volume "Bounding volume") and [cursors](https://en.wikipedia.org/wiki/Cursor_\(computers\) "Cursor (computers)") on systems without [alpha channels](https://en.wikipedia.org/wiki/Alpha_compositing "Alpha compositing") or overlay planes.

## Encodings

It is also called "not left-right arrow" (`\nleftrightarrow`) in [LaTeX](https://en.wikipedia.org/wiki/LaTeX "LaTeX") -based markdown (${\displaystyle \nleftrightarrow }$). Apart from the ASCII codes, the operator is encoded at U+22BB ⊻ XOR (&veebar;) and U+2295 ⊕ CIRCLED PLUS (&CirclePlus;, &oplus;), both in block [mathematical operators](https://en.wikipedia.org/wiki/Mathematical_operators_and_symbols_in_Unicode#Mathematical_Operators "Mathematical operators and symbols in Unicode").

[^1]: Germundsson, Roger; Weisstein, Eric. ["XOR"](http://mathworld.wolfram.com/XOR.html). *[MathWorld](https://en.wikipedia.org/wiki/MathWorld "MathWorld")*. [Wolfram Research](https://en.wikipedia.org/wiki/Wolfram_Research "Wolfram Research"). Retrieved 17 June 2015.

[^2]: Bocheński, J. M. (1949). [*Précis de logique mathématique*](https://burjcdigital.urjc.es/bitstream/handle/10115/1425/PRECIS_DE_LOGIQUE_MATHEMATIQUE.pdf?sequence=1&isAllowed=y) (PDF) (in French). The Netherlands: F. G. Kroonder, Bussum, Pays-Bas. Translated as Bocheński, J. M. (1959). [*A Precis of Mathematical Logic*](https://archive.org/details/precisofmathemat0000boch/). Translated by Bird, O. Dordrecht, Holland: D. Reidel Publishing Company. [doi](https://en.wikipedia.org/wiki/Doi_\(identifier\) "Doi (identifier)"):[10.1007/978-94-017-0592-9](https://doi.org/10.1007%2F978-94-017-0592-9). [ISBN](https://en.wikipedia.org/wiki/ISBN_\(identifier\) "ISBN (identifier)") [978-90-481-8329-6](https://en.wikipedia.org/wiki/Special:BookSources/978-90-481-8329-6 "Special:BookSources/978-90-481-8329-6").

[^3]: Joux, Antoine (2009). ["9.2: Algebraic normal forms of Boolean functions"](https://books.google.com/books?id=buQajqt-_iUC&pg=PA285). *Algorithmic Cryptanalysis*. CRC Press. pp. 285–286. [ISBN](https://en.wikipedia.org/wiki/ISBN_\(identifier\) "ISBN (identifier)") [9781420070033](https://en.wikipedia.org/wiki/Special:BookSources/9781420070033 "Special:BookSources/9781420070033").

[^4]: [Aloni, Maria](https://en.wikipedia.org/wiki/Maria_Aloni "Maria Aloni") (2016). ["Disjunction"](https://plato.stanford.edu/archives/win2016/entries/disjunction/). In Zalta, Edward N. (ed.). *The Stanford Encyclopedia of Philosophy* (Winter 2016 ed.). Metaphysics Research Lab, Stanford University. Retrieved 2020-09-03.

[^5]: Jennings quotes numerous authors saying that the word "or" has an exclusive sense. See Chapter 3, "The First Myth of 'Or'":  
Jennings, R. E. (1994). *The Genealogy of Disjunction*. New York: Oxford University Press.

[^6]: Boole, G. (1847). [*The Mathematical Analysis of Logic, Being an Essay Towards a Calculus of Deductive Reasoning*](https://archive.org/details/mathematicalanal00booluoft). Cambridge/London: Macmillan, Barclay, & Macmillan/George Bell. p. 17.

[^7]: Enderton, H. (2001) \[1972\]. *A Mathematical Introduction to Logic* (2 ed.). San Diego, New York, Boston, London, Toronto, Sydney and Tokyo: A Harcourt Science and Technology Company. p. 51.

[^8]: Rautenberg, W. (2010) \[2006\]. *A Concise Introduction to Mathematical Logic* (3 ed.). New York, Dordrecht, Heidelberg and London: Springer. p. 3.

[^9]: Ladd, Christine (1883). ["On the Algebra of Logic"](https://archive.org/details/studiesinlogic00peiruoft/page/16). In Peirce, C. S. (ed.). *Studies in Logic by Members of the Johns Hopkins University*. Boston: Little, Brown & Company. pp. 17–71.

[^10]: Schröder, E. (1890). *Vorlesungen über die Algebra der Logik (Exakte Logik), Erster Band* (in German). Leipzig: Druck und Verlag B. G. Teubner. Reprinted by Thoemmes Press in 2000.

[^11]: Peano, G. (1894). *Notations de logique mathématique. Introduction au formulaire de mathématique*. Turin: Fratelli Boccna. Reprinted in Peano, G. (1958). [*Opere Scelte, Volume II*](https://archive.org/details/operescelte0002gius/page/n5/mode/2up). Roma: Edizioni Cremonese. pp. 123–176.

[^12]: ГРАДШТЕЙН, И. С. (1959) \[1936\]. [*ПРЯМАЯ И ОБРАТНАЯ ТЕОРЕМЫ: ЭЛЕМЕНТЫ АЛГЕБРЫ ЛОГИКИ*](https://www.mathedu.ru/text/gradshteyn_pryamaya_i_obratnaya_teoremy_1959/p0/) (in Russian) (3 ed.). МОСКВА: ГОСУДАРСТВЕННОЕ ИЗДАТЕЛЬСТВО ФИЗИКа-МАТЕМАТИЧЕСКОЙ ЛИТЕРАТУРЫ. Translated as Gradshtein, I. S. (1963). *Direct and Converse Theorems: The Elements of Symbolic Logic*. Translated by Boddington, T. Oxford, London, New York and Paris: Pergamon Press.

[^13]: [Shannon, C. E.](https://en.wikipedia.org/wiki/Claude_Elwood_Shannon "Claude Elwood Shannon") (1938). ["A Symbolic Analysis of Relay and Switching Circuits"](https://www.cs.virginia.edu/~evans/greatworks/shannon38.pdf) (PDF). *Transactions of the American Institute of Electrical Engineers*. **57** (12): 713–723. [doi](https://en.wikipedia.org/wiki/Doi_\(identifier\) "Doi (identifier)"):[10.1109/T-AIEE.1938.5057767](https://doi.org/10.1109%2FT-AIEE.1938.5057767). [hdl](https://en.wikipedia.org/wiki/Hdl_\(identifier\) "Hdl (identifier)"):[1721.1/11173](https://hdl.handle.net/1721.1%2F11173). [S2CID](https://en.wikipedia.org/wiki/S2CID_\(identifier\) "S2CID (identifier)") [51638483](https://api.semanticscholar.org/CorpusID:51638483).

[^14]: Huntington, E. V. (1904). "Sets of Independent Postulates for the Algebra of Logic". *Transactions of the American Mathematical Society*. **5** (3): 288–309. [doi](https://en.wikipedia.org/wiki/Doi_\(identifier\) "Doi (identifier)"):[10.1090/S0002-9947-1904-1500675-4](https://doi.org/10.1090%2FS0002-9947-1904-1500675-4).

[^15]: Leibniz, G. W. (1890) \[16??/17??\]. Gerhardt, C. I. (ed.). [*Die philosophischen Schriften, Siebter Band*](https://archive.org/details/diephilosophisc01leibgoog/page/n11/mode/2up) (in German). Berlin: Weidmann. p. 237. Retrieved 7 July 2023.

[^16]: Huntington, E. V. (1933). "New Sets of Independent Postulates for the Algebra of Logic, With Special Reference to Whitehead and Russell's Principia Mathematica". *Transactions of the American Mathematical Society*. **35** (1): 274–304.

[^17]: Church, A. (1996) \[1944\]. *Introduction to Mathematical Logic*. New Jersey: Princeton University Press. p. 37.

[^18]: Craig, Edward (1998). [*Routledge Encyclopedia of Philosophy, Volume 8*](https://books.google.com/books?id=mxpFwcAplaAC&pg=PA496). [Taylor & Francis](https://en.wikipedia.org/wiki/Taylor_&_Francis "Taylor & Francis"). p. 496. [ISBN](https://en.wikipedia.org/wiki/ISBN_\(identifier\) "ISBN (identifier)") [978-0-41507310-3](https://en.wikipedia.org/wiki/Special:BookSources/978-0-41507310-3 "Special:BookSources/978-0-41507310-3").

[^19]: [Łukasiewicz, Jan](https://en.wikipedia.org/wiki/Jan_%C5%81ukasiewicz "Jan Łukasiewicz") (1929). *Elementy logiki matematycznej* \[*Elements of Mathematical Logic*\] (in Polish) (1 ed.). Warsaw, Poland: [Państwowe Wydawnictwo Naukowe](https://en.wikipedia.org/wiki/Pa%C5%84stwowe_Wydawnictwo_Naukowe "Państwowe Wydawnictwo Naukowe").

[^20]: [Kernighan, Brian W.](https://en.wikipedia.org/wiki/Brian_Kernighan "Brian Kernighan"); [Ritchie, Dennis M.](https://en.wikipedia.org/wiki/Dennis_Ritchie "Dennis Ritchie") (1978). ["2.9: Bitwise logical operators"](https://archive.org/details/TheCProgrammingLanguageFirstEdition/page/n51). [*The C Programming Language*](https://en.wikipedia.org/wiki/The_C_Programming_Language "The C Programming Language"). Prentice-Hall. pp. 44–46.

[^21]: [Weisstein, Eric W.](https://en.wikipedia.org/wiki/Eric_W._Weisstein "Eric W. Weisstein") ["Symmetric Difference"](https://mathworld.wolfram.com/SymmetricDifference.html). *[MathWorld](https://en.wikipedia.org/wiki/MathWorld "MathWorld")*.

[^22]: Davies, Robert B (28 February 2002). ["Exclusive OR (XOR) and hardware random number generators"](http://www.robertnz.net/pdf/xor2.pdf) (PDF). Retrieved 28 August 2013.

[^23]: Nobel, Rickard (26 July 2011). ["How RAID 5 actually works"](http://rickardnobel.se/how-raid5-works). Retrieved 23 March 2017.