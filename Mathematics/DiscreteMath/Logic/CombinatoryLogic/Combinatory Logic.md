---
date: 2026-04-18
---
**Combinatory Logic** is a variant of mathematical [[Logic]] that achieves the same power as [[Lambda Calculus]] but eliminates the need for [[Mathematics/DiscreteMath/Logic/LambdaCalculus/Atom|variables (atoms)]].

# Birds
| Bird            | Arity      | Function Abstraction   | Symbol | AN⁴   | CR¹              | CH²        |
| :-------------- | :--------- | :--------------------- | :----- | :---- | :--------------- | :--------- |
| Identity        | Unary      | `λa.a`                 | **I**  | -     | `SKK`            | `SKK`      |
| Kestrel         | Binary     | `λab.a`                | **K**  | -     | `K`              | `K`        |
| Kite            | Binary     | `λab.b`                | **κ**  | -     | `KI`             | `KI`       |
| Warbler         | Binary     | `λab.abb`              | **W**  | 1y2   | `C(BMR)`         | `CSK`      |
| Cardinal        | Ternary    | `λabc.acb`             | **C**  | 2y2   | `S(BBS)(KK)`     | `B(ΦBS)KK` |
| Bluebird        | Ternary    | `λabc.a(bc)`           | **B**  | 1y11  | `S(KS)K`         | `S(KS)K`   |
| Blackbird       | Quaternary | `λabcd.a(bcd)`         | **B₁** | 2y12  | `BBB`            | `DB`       |
| Bunting         | Quinary    | `λabcde.a(bcde)`       | **B₂** | 3y13  | `B(BBB)B`        | `DB₁`      |
| Becard          | Quaternary | `λabcd.a(b(cd))`       | **B₃** | 1y111 | `B(BB)B`         | `BDB`      |
| Starling        | Ternary    | `λabc.ac(bc)`          | **S**  | 1y21  | `S`              | `S`        |
| Violet Starling | Ternary    | `λabc.a(bc)c`          | **Σ**  | 1y12  | -                | ?          |
| Dove            | Quaternary | `λabcd.ab(cd)`         | **D**  | 2y21  | `BB`             | `BB`       |
| Zebra Dove      | Quaternary | `λabcd.a(bc)d`         | **Δ**  | 2y12  | -                | ?          |
| Phoenix         | Quaternary | `λabcd.a(bd)(cd)`      | **Φ**  | 1y121 | -                | `B₁SB`     |
| Psi             | Quaternary | `λabcd.a(bc)(bd)`      | **Ψ**  | 2y21  | -                | `B(SΦCB)B` |
| Dickcissel      | Quinary    | `λabcde.abc(de)`       | **D₁** | 3y31  | `B(BB)`          | `BD`       |
| Dovekie         | Quinary    | `λabcde.a(bc)(de)`     | **D₂** | 2y211 | `BB(BB)`         | `DD`       |
| Eagle           | Quinary    | `λabcde.ab(cde)`       | **E**  | 3y22  | `B(BBB)`         | `BB₁`      |
| Golden Eagle    | Quinary    | `λabcde.a(bcd)e`       | **ε**  | 3y22  | -                | ?          |
| Pheasant        | Quinary    | `λabcde.a(bde)(cde)`   | **Φ₁** | 2y222 | -                | `BΦΦ`      |
| Bald Eagle      | Septenary  | `λabcdefg.a(bcd)(efg)` | **Ê**  | 4y222 | `B(BBB)(B(BBB))` | `D₂D₂D`    |