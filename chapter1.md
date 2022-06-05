# Fundamental Definition

A *relational schema* (called a *relation scheme* in Maier[1]) $R$ is a finite set of *attribute names* $\{A_1, A_2, \ldots, A_n\}$. Each attribute name $A_i$ has an associated set $D_i, 1\leq i \leq n$ called the *domain* of $A_i$. We denote the domain of $A_i$ by $\text{dom}(A_i)$. Attribute names  may be referred to as *columns*, *attributes* or *attribute symbols*(Maier[1]). The domains are arbitrary, non-empy sets, finite or countably infinite (or for the mathematicians: $0 <|\text{dom}(A_i)| \leq \aleph_0$, where $\aleph_0$ is the cardinality of a countably infinite set). 

Let $\bf{D} = D_1 \cup D_2 \cup \ldots \cup D_n$, a *relation* $r$ on a relational schema $R$ is a finite set of mappings $\{ t_1, t_2, \ldots, t_n\}$ from $R$ to $\bf{D}$ (written $t_i:R \rightarrow \bf{D}$) such that for each mapping $t \in r, t(A_i) \in D_i$, where $1 \leq i \leq n$. These mappings are referred to as *rows* (Maier[1]).



***Definition 1.1*** A *relational table* (or just a *table* when the context is clear) is a tuple $(R, r)$ where $R$ is a relational schema(a set of columns) and $r$ is a relation (a set of rows)

For example consider the following table of 

***Definition 2.2*** A *key* of a relational table $(R, r)$ is a subset $K$ of $R$ such that for any distinct tuples $t_1$ and $t_2$ in $r$, $t_1(K) \neq t_2(K)$ and no proper subset $K^\prime$ of $K$ shares this property 

The last part of the definition is necessary to ensure $K$ is the minimal set of columns that allow us to uniquely identify each row in the table. 

***Example***
Airline Schedule table inspired by Maier[1]

| NUMBER | FROM | TO  | DEPARTS | ARRIVES |
| ------ | ---- | --- | ------- | ------- |
| 83 | Toronto | Montreal | 10:30a | 12:43p |
| 84 | Montreal | Toronto | 4:00p | 5:55p |
| 109 | Toronto | Vancouver | 9:50p | 4:52a |
| 213 | Toronto | Regina | 10:43a | 4:30p |

Generalized if we have a relational schema $R = \{A_1, A_2, A_3, A_4, A_5\}$ and a relation $r = \{t_1, t_2, t_3, t_4\}$ we generate the following table $(R, r)$.

| $A_1$ | $A_2$ | $A_3$  | $A_4$ | $A_5$ |
| ------ | ---- | --- | ------- | ------- |
| $t_1(A_1)$ | $t_1(A_2)$ | $t_1(A_3)$ | $t_1(A_4)$ | $t_1(A_5)$ |
| $t_2(A_1)$ | $t_2(A_2)$ | $t_2(A_3)$ | $t_2(A_4)$ | $t_2(A_5)$ |
| $t_3(A_1)$ | $t_3(A_2)$ | $t_3(A_3)$ | $t_3(A_4)$ | $t_3(A_5)$ |
| $t_4(A_1)$ | $t_4(A_2)$ | $t_4(A_3)$ | $t_4(A_4)$ | $t_4(A_5)$ |

Tying it together: [NOTE TO SELF: it would be cool to hover over the former table and have it fill in the below]

| $A_1=$ NUMBER | $A_2=$ FROM | $A_3=$  TO  | $A_4=$ DEPARTS | $A_5=$ ARRIVES |
| ------ | ---- | --- | ------- | ------- |
| $t_1(A_1)=$ 83 | $t_1(A_2) =$ Toronto | $t_1(A_3)=$ Montreal | $t_1(A_4)=$ 10:30a | $t_1(A_5)=$  12:43p|
| $t_2(A_1)=$ 84 | $t_2(A_2)=$ Montreal | $t_2(A_3)=$ Toronto | $t_2(A_4)=$ 4:00p | $t_2(A_5)=$ 5:55p |
| $t_3(A_1)=$ 109 | $t_3(A_2)=$ Toronto | $t_3(A_3)=$ Vancouver | $t_3(A_4)=$ 9:50p | $t_3(A_5)=$ 4:52a |
| $t_4(A_1)=$ 213 | $t_4(A_2)=$ Toronto | $t_4(A_3)=$ Regina | $t_4(A_4)=$ 10:43a | $t_4(A_5)=$ 4:30p |

Furthermore, the attributes in $R$ have the following domains.

1. $\text{dom}(A_1) = \{ n \in \mathbb{N} \;|\; n < 1000\}$, where $\mathbb{N}$ is the integers larger than $0$.
2. $\text{dom}(A_2) = \text{dom}(A_3) = \{x \ | \ x \text{ is a canadian city}\}$
3. $\text{dom}(A_4) = \text{dom}(A_5) = \{x  \ | \ x \text{ is a time during the day} \} $

***Example*** Returning to an expanded Airline Schedule table

| NUMBER | FROM | TO  | DEPARTS | ARRIVES |
| ------ | ---- | --- | ------- | ------- |
| 83 | Toronto | Montreal | 10:30a | 12:43p |
| 84 | Montreal | Toronto | 4:00p | 5:55p |
| 109 | Toronto | Vancouver | 9:50p | 4:52a |
| 213 | Toronto | Regina | 10:43a | 4:30p |
| 214 | Regina | Toronto | 7:00 p | 1:30a |
| 338 | Winnepeg | Toronto | 11:15 p | 2:57 |

Above $R =$ $\{$ NUMBER, FROM, TO, DEPARTS, ARRIVES $\}$