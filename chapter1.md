# Fundamental Definition

A *relational schema* (called a *relation scheme* in Maier[1]) $R$ is a finite set of *attribute names* $\{A_1, A_2, \ldots, A_n\}$. Each attribute name $A_i$ has an associated set $D_i, 1\leq i \leq n$ called the *domain* of $A_i$. We denote the domain of $A_i$ by $\text{dom}(A_i)$. Attribute names  may be referred to as *columns*, *attributes* or *attribute symbols*(Maier[1]). The domains are arbitrary, non-empy sets, finite or countably infinite (or for the mathematicians: $0 <|\text{dom}(A_i)| \leq \aleph_0$, where $\aleph_0$ is the cardinality of a countably infinite set). 

Let $\bold{D} = D_1 \cup D_2 \cup \ldots \cup D_n$, a *relation* $r$ on a relational schema $R$ is a finite set of mappings $\{ t_1, t_2, \ldots, t_n\}$ from $R$ to $\bold{D}$ (written $t_i:R \rightarrow \bold{D}$) such that for each mapping $t \in r, t(A_i) \in D_i$, where $1 \leq i \leq n$. These mappings are referred to as *rows* (Maier[1]).



***Definition 1.1*** A *relational table* is a tuple $(R, r)$ where $R$ is a relational schema(a set of columns) and $r$ is a relation (a set of rows)