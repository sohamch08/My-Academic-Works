---
tag: matching
---
# Hall's Matching Condition

>[!theorem] Theorem (Hall's Theorem) - P. Hall (1935)
>An $X,Y$-[[Bigraph]] $G$ has a [[Matching]] that [saturate](./Matching.md) $X$ if and only if $|N(S)|\geq |S|$ for all $S\subseteq X$.

***Proof:*** 
**Necessity:** The $|S|$ vertices matched to $S$ must lie in [$N(S)$](Neighbor.md) for all $S\subseteq X$.
**Sufficiency:** To prove that Hall's Condition is sufficient we prove the contrapositive. If $M$ is a [[Maximum Matching]] in $G$ and $M$ does not [saturate](./Matching.md) $X$, then we obtain a set $S\subseteq X$ such that $N(S)\leq |S|$. 
Let $u\in X$ be a vertex [unsaturated](./Matching.md) by $M$. Among all the vertices reachable from $u$ by $M$-[[Alternating Path]]s in $G$ let $S$ consists of those in $X$ and let $T$ consists of those in $Y$. Note that $u\in S$. 
```tikz
\begin{document}
	\begin{tikzpicture}[scale=2.5, font=\LARGE]
		\foreach \i in {1,2,3,4,5,6,7}{
			\filldraw[black] (-\i,1) circle (2pt);
		}
		\foreach \i in {0,1,2,3,4,5,6,7}{
			\filldraw[black] (-\i+1,-1) circle (2pt);
		}
		\foreach \i in {1,2,3}{
			\draw (-7+\i,-1) -- (-6+\i,1);
		}
		\foreach \i in {1,2,3,4,5,6}{
			\draw[line width=0.7mm] (-\i,-1) -- (-\i,1);
		}
		\foreach \i in {1,2,5,7}{
			\draw (-5,-1) -- (-\i,1);
		}
		\draw (-4,-1) -- (-5,1);
		\draw (-2,1) -- (0,-1);
		\draw (-1,1) -- (1,-1);
		\draw (-7,1) node [xshift=-0.5cm]{$u$};
		\draw (-7.5,1) node [xshift=-1cm]{$X$};
		\draw (-7.5,-1) node [xshift=-1cm]{$Y$};
		\draw (-7,1.2) -- (-4,1.2) node [midway, above]{$S$};
		\draw (-6,-1.2) -- (-4,-1.2) node [midway, below]{$T=N(S)$};
	\end{tikzpicture}
\end{document}
```

We claim that $M$ matches $T$ with $S-\{u\}$. The $M$-[[Alternating Path]]s from $u$ reach $Y$ along edges not in $M$ and return to $X$ along edges in $M$. Hence every vertex of $S-\{u\}$ is reached by an edge in $M$ from a vertex in $T$. Since there is no $M$-[[Augmenting Path]] in $G$ since $M$ is a [[Maximum Matching]] by the theorem in [[Augmenting Path]], every vertex of $T$ is [saturated](./Matching.md); thus an $M$-[[Alternating Path]] reaching $y\in T$ extends via $M$ to a vertex of $S$. Hence these edges of $M$ yield a bijection from $T$ to $S-\{u\}$ and we have $|T|=|S-\{u\}|$.
The [[Matching]] between $T$ and $S-\{u\}$ yields $T\subseteq N(S)$. In fact, $T=N(S)$. Suppose that $y\in Y-T$ has a [[Neighbor]] $v\in S$. The edge $vy$ cannot be in $M$ since $u$ is [unsaturated](./Matching.md) and the rest of $S$ is matched to $T$ by $M$ (Since $S-\{u\}$ is matched to $T$ by $M$ if the edge $vy$ is in $M$ then the vertex $v$ will be [[Incident]] on two edges in $M$ which is not possible). Thus adding $vy$ to an $M$-[[Alternating Path]] reaching $v$ yields an $M$-[[Alternating Path]] to $y$. This contradicts $y\notin T$ and hence $vy$ cannot exists.
With $T=N(S)$ we have proved that $|N(S)|=|T|=|S|-1<|S|$ for this choice of $S$. This completes the proof of the contrapositive. $\blacksquare$

>Note also that the statement and proof permit multiple edges.

>[!corollary] 
>For $k>0$ every $k$-[[Regular]] [[Bipartite]] [[Graph]] has a [[Perfect Matching]]

***Proof:*** Let $G$ be a $k$-[[Regular]] $X,Y$-[[Bigraph]]. Counting the edges by endpoints in $X$ and by endpoints in $Y$ shows that $k|X|=k|Y|$ so $|X|=|Y|$. Hence it suffices to verify Hall's Condition; a [[Matching]] that [saturates](./Matching.md) $X$ will also [saturate](./Matching.md) $Y$ and be a [[Perfect Matching]].
Consider $S\subseteq X$. Let $m$ be the number of edges from $S$ to $N(S)$. Since $G$ is $k$-[[Regular]] $m=k|S|$. These $m$ edges are [[Incident]] to $N(S)$, so $m\leq k|N(S)|$. Hence $k|S|\leq k|N(S)|$ which yields $|N(S)|\geq |S|$ when $k>0$. Having chosen $S\subseteq X$ arbitrarily we have established Hall's condition. $\blacksquare$
>One can also use contradiction here. Assuming that $G$ has no [[Perfect Matching]] yields a set $S\subseteq X$ such that $|N(S)|<|S|$. The argument obtaining contradiction amounts to a rewording of the direct proof given above










































$$%---------------------------------------
% BlackBoard Math Fonts :-
%---------------------------------------

%Captital Letters
\newcommand{\bbA}{\mathbb{A}}	\newcommand{\bbB}{\mathbb{B}}
\newcommand{\bbC}{\mathbb{C}}	\newcommand{\bbD}{\mathbb{D}}
\newcommand{\bbE}{\mathbb{E}}	\newcommand{\bbF}{\mathbb{F}}
\newcommand{\bbG}{\mathbb{G}}	\newcommand{\bbH}{\mathbb{H}}
\newcommand{\bbI}{\mathbb{I}}	\newcommand{\bbJ}{\mathbb{J}}
\newcommand{\bbK}{\mathbb{K}}	\newcommand{\bbL}{\mathbb{L}}
\newcommand{\bbM}{\mathbb{M}}	\newcommand{\bbN}{\mathbb{N}}
\newcommand{\bbO}{\mathbb{O}}	\newcommand{\bbP}{\mathbb{P}}
\newcommand{\bbQ}{\mathbb{Q}}	\newcommand{\bbR}{\mathbb{R}}
\newcommand{\bbS}{\mathbb{S}}	\newcommand{\bbT}{\mathbb{T}}
\newcommand{\bbU}{\mathbb{U}}	\newcommand{\bbV}{\mathbb{V}}
\newcommand{\bbW}{\mathbb{W}}	\newcommand{\bbX}{\mathbb{X}}
\newcommand{\bbY}{\mathbb{Y}}	\newcommand{\bbZ}{\mathbb{Z}}

%---------------------------------------
% MathCal Fonts :-
%---------------------------------------

%Captital Letters
\newcommand{\mcA}{\mathcal{A}}	\newcommand{\mcB}{\mathcal{B}}
\newcommand{\mcC}{\mathcal{C}}	\newcommand{\mcD}{\mathcal{D}}
\newcommand{\mcE}{\mathcal{E}}	\newcommand{\mcF}{\mathcal{F}}
\newcommand{\mcG}{\mathcal{G}}	\newcommand{\mcH}{\mathcal{H}}
\newcommand{\mcI}{\mathcal{I}}	\newcommand{\mcJ}{\mathcal{J}}
\newcommand{\mcK}{\mathcal{K}}	\newcommand{\mcL}{\mathcal{L}}
\newcommand{\mcM}{\mathcal{M}}	\newcommand{\mcN}{\mathcal{N}}
\newcommand{\mcO}{\mathcal{O}}	\newcommand{\mcP}{\mathcal{P}}
\newcommand{\mcQ}{\mathcal{Q}}	\newcommand{\mcR}{\mathcal{R}}
\newcommand{\mcS}{\mathcal{S}}	\newcommand{\mcT}{\mathcal{T}}
\newcommand{\mcU}{\mathcal{U}}	\newcommand{\mcV}{\mathcal{V}}
\newcommand{\mcW}{\mathcal{W}}	\newcommand{\mcX}{\mathcal{X}}
\newcommand{\mcY}{\mathcal{Y}}	\newcommand{\mcZ}{\mathcal{Z}}



%---------------------------------------
% Bold Math Fonts :-
%---------------------------------------

%Captital Letters
\newcommand{\bmA}{\boldsymbol{A}}	\newcommand{\bmB}{\boldsymbol{B}}
\newcommand{\bmC}{\boldsymbol{C}}	\newcommand{\bmD}{\boldsymbol{D}}
\newcommand{\bmE}{\boldsymbol{E}}	\newcommand{\bmF}{\boldsymbol{F}}
\newcommand{\bmG}{\boldsymbol{G}}	\newcommand{\bmH}{\boldsymbol{H}}
\newcommand{\bmI}{\boldsymbol{I}}	\newcommand{\bmJ}{\boldsymbol{J}}
\newcommand{\bmK}{\boldsymbol{K}}	\newcommand{\bmL}{\boldsymbol{L}}
\newcommand{\bmM}{\boldsymbol{M}}	\newcommand{\bmN}{\boldsymbol{N}}
\newcommand{\bmO}{\boldsymbol{O}}	\newcommand{\bmP}{\boldsymbol{P}}
\newcommand{\bmQ}{\boldsymbol{Q}}	\newcommand{\bmR}{\boldsymbol{R}}
\newcommand{\bmS}{\boldsymbol{S}}	\newcommand{\bmT}{\boldsymbol{T}}
\newcommand{\bmU}{\boldsymbol{U}}	\newcommand{\bmV}{\boldsymbol{V}}
\newcommand{\bmW}{\boldsymbol{W}}	\newcommand{\bmX}{\boldsymbol{X}}
\newcommand{\bmY}{\boldsymbol{Y}}	\newcommand{\bmZ}{\boldsymbol{Z}}
%Small Letters
\newcommand{\bma}{\boldsymbol{a}}	\newcommand{\bmb}{\boldsymbol{b}}
\newcommand{\bmc}{\boldsymbol{c}}	\newcommand{\bmd}{\boldsymbol{d}}
\newcommand{\bme}{\boldsymbol{e}}	\newcommand{\bmf}{\boldsymbol{f}}
\newcommand{\bmg}{\boldsymbol{g}}	\newcommand{\bmh}{\boldsymbol{h}}
\newcommand{\bmi}{\boldsymbol{i}}	\newcommand{\bmj}{\boldsymbol{j}}
\newcommand{\bmk}{\boldsymbol{k}}	\newcommand{\bml}{\boldsymbol{l}}
\newcommand{\bmm}{\boldsymbol{m}}	\newcommand{\bmn}{\boldsymbol{n}}
\newcommand{\bmo}{\boldsymbol{o}}	\newcommand{\bmp}{\boldsymbol{p}}
\newcommand{\bmq}{\boldsymbol{q}}	\newcommand{\bmr}{\boldsymbol{r}}
\newcommand{\bms}{\boldsymbol{s}}	\newcommand{\bmt}{\boldsymbol{t}}
\newcommand{\bmu}{\boldsymbol{u}}	\newcommand{\bmv}{\boldsymbol{v}}
\newcommand{\bmw}{\boldsymbol{w}}	\newcommand{\bmx}{\boldsymbol{x}}
\newcommand{\bmy}{\boldsymbol{y}}	\newcommand{\bmz}{\boldsymbol{z}}

%---------------------------------------
% Scr Math Fonts :-
%---------------------------------------

\newcommand{\sA}{{\mathscr{A}}}   \newcommand{\sB}{{\mathscr{B}}}
\newcommand{\sC}{{\mathscr{C}}}   \newcommand{\sD}{{\mathscr{D}}}
\newcommand{\sE}{{\mathscr{E}}}   \newcommand{\sF}{{\mathscr{F}}}
\newcommand{\sG}{{\mathscr{G}}}   \newcommand{\sH}{{\mathscr{H}}}
\newcommand{\sI}{{\mathscr{I}}}   \newcommand{\sJ}{{\mathscr{J}}}
\newcommand{\sK}{{\mathscr{K}}}   \newcommand{\sL}{{\mathscr{L}}}
\newcommand{\sM}{{\mathscr{M}}}   \newcommand{\sN}{{\mathscr{N}}}
\newcommand{\sO}{{\mathscr{O}}}   \newcommand{\sP}{{\mathscr{P}}}
\newcommand{\sQ}{{\mathscr{Q}}}   \newcommand{\sR}{{\mathscr{R}}}
\newcommand{\sS}{{\mathscr{S}}}   \newcommand{\sT}{{\mathscr{T}}}
\newcommand{\sU}{{\mathscr{U}}}   \newcommand{\sV}{{\mathscr{V}}}
\newcommand{\sW}{{\mathscr{W}}}   \newcommand{\sX}{{\mathscr{X}}}
\newcommand{\sY}{{\mathscr{Y}}}   \newcommand{\sZ}{{\mathscr{Z}}}


%---------------------------------------
% Math Fraktur Font
%---------------------------------------

%Captital Letters
\newcommand{\mfA}{\mathfrak{A}}	\newcommand{\mfB}{\mathfrak{B}}
\newcommand{\mfC}{\mathfrak{C}}	\newcommand{\mfD}{\mathfrak{D}}
\newcommand{\mfE}{\mathfrak{E}}	\newcommand{\mfF}{\mathfrak{F}}
\newcommand{\mfG}{\mathfrak{G}}	\newcommand{\mfH}{\mathfrak{H}}
\newcommand{\mfI}{\mathfrak{I}}	\newcommand{\mfJ}{\mathfrak{J}}
\newcommand{\mfK}{\mathfrak{K}}	\newcommand{\mfL}{\mathfrak{L}}
\newcommand{\mfM}{\mathfrak{M}}	\newcommand{\mfN}{\mathfrak{N}}
\newcommand{\mfO}{\mathfrak{O}}	\newcommand{\mfP}{\mathfrak{P}}
\newcommand{\mfQ}{\mathfrak{Q}}	\newcommand{\mfR}{\mathfrak{R}}
\newcommand{\mfS}{\mathfrak{S}}	\newcommand{\mfT}{\mathfrak{T}}
\newcommand{\mfU}{\mathfrak{U}}	\newcommand{\mfV}{\mathfrak{V}}
\newcommand{\mfW}{\mathfrak{W}}	\newcommand{\mfX}{\mathfrak{X}}
\newcommand{\mfY}{\mathfrak{Y}}	\newcommand{\mfZ}{\mathfrak{Z}}
%Small Letters
\newcommand{\mfa}{\mathfrak{a}}	\newcommand{\mfb}{\mathfrak{b}}
\newcommand{\mfc}{\mathfrak{c}}	\newcommand{\mfd}{\mathfrak{d}}
\newcommand{\mfe}{\mathfrak{e}}	\newcommand{\mff}{\mathfrak{f}}
\newcommand{\mfg}{\mathfrak{g}}	\newcommand{\mfh}{\mathfrak{h}}
\newcommand{\mfi}{\mathfrak{i}}	\newcommand{\mfj}{\mathfrak{j}}
\newcommand{\mfk}{\mathfrak{k}}	\newcommand{\mfl}{\mathfrak{l}}
\newcommand{\mfm}{\mathfrak{m}}	\newcommand{\mfn}{\mathfrak{n}}
\newcommand{\mfo}{\mathfrak{o}}	\newcommand{\mfp}{\mathfrak{p}}
\newcommand{\mfq}{\mathfrak{q}}	\newcommand{\mfr}{\mathfrak{r}}
\newcommand{\mfs}{\mathfrak{s}}	\newcommand{\mft}{\mathfrak{t}}
\newcommand{\mfu}{\mathfrak{u}}	\newcommand{\mfv}{\mathfrak{v}}
\newcommand{\mfw}{\mathfrak{w}}	\newcommand{\mfx}{\mathfrak{x}}
\newcommand{\mfy}{\mathfrak{y}}	\newcommand{\mfz}{\mathfrak{z}}

%---------------------------------------
% Bar
%---------------------------------------

%Captital Letters
\newcommand{\ovA}{\overline{A}}	\newcommand{\ovB}{\overline{B}}
\newcommand{\ovC}{\overline{C}}	\newcommand{\ovD}{\overline{D}}
\newcommand{\ovE}{\overline{E}}	\newcommand{\ovF}{\overline{F}}
\newcommand{\ovG}{\overline{G}}	\newcommand{\ovH}{\overline{H}}
\newcommand{\ovI}{\overline{I}}	\newcommand{\ovJ}{\overline{J}}
\newcommand{\ovK}{\overline{K}}	\newcommand{\ovL}{\overline{L}}
\newcommand{\ovM}{\overline{M}}	\newcommand{\ovN}{\overline{N}}
\newcommand{\ovO}{\overline{O}}	\newcommand{\ovP}{\overline{P}}
\newcommand{\ovQ}{\overline{Q}}	\newcommand{\ovR}{\overline{R}}
\newcommand{\ovS}{\overline{S}}	\newcommand{\ovT}{\overline{T}}
\newcommand{\ovU}{\overline{U}}	\newcommand{\ovV}{\overline{V}}
\newcommand{\ovW}{\overline{W}}	\newcommand{\ovX}{\overline{X}}
\newcommand{\ovY}{\overline{Y}}	\newcommand{\ovZ}{\overline{Z}}
%Small Letters
\newcommand{\ova}{\overline{a}}	\newcommand{\ovb}{\overline{b}}
\newcommand{\ovc}{\overline{c}}	\newcommand{\ovd}{\overline{d}}
\newcommand{\ove}{\overline{e}}	\newcommand{\ovf}{\overline{f}}
\newcommand{\ovg}{\overline{g}}	\newcommand{\ovh}{\overline{h}}
\newcommand{\ovi}{\overline{i}}	\newcommand{\ovj}{\overline{j}}
\newcommand{\ovk}{\overline{k}}	\newcommand{\ovl}{\overline{l}}
\newcommand{\ovm}{\overline{m}}	\newcommand{\ovn}{\overline{n}}
\newcommand{\ovo}{\overline{o}}	\newcommand{\ovp}{\overline{p}}
\newcommand{\ovq}{\overline{q}}	\newcommand{\ovr}{\overline{r}}
\newcommand{\ovs}{\overline{s}}	\newcommand{\ovt}{\overline{t}}
\newcommand{\ovu}{\overline{u}}	\newcommand{\ovv}{\overline{v}}
\newcommand{\ovw}{\overline{w}}	\newcommand{\ovx}{\overline{x}}
\newcommand{\ovy}{\overline{y}}	\newcommand{\ovz}{\overline{z}}

%---------------------------------------
% Tilde
%---------------------------------------

%Captital Letters
\newcommand{\tdA}{\tilde{A}}	\newcommand{\tdB}{\tilde{B}}
\newcommand{\tdC}{\tilde{C}}	\newcommand{\tdD}{\tilde{D}}
\newcommand{\tdE}{\tilde{E}}	\newcommand{\tdF}{\tilde{F}}
\newcommand{\tdG}{\tilde{G}}	\newcommand{\tdH}{\tilde{H}}
\newcommand{\tdI}{\tilde{I}}	\newcommand{\tdJ}{\tilde{J}}
\newcommand{\tdK}{\tilde{K}}	\newcommand{\tdL}{\tilde{L}}
\newcommand{\tdM}{\tilde{M}}	\newcommand{\tdN}{\tilde{N}}
\newcommand{\tdO}{\tilde{O}}	\newcommand{\tdP}{\tilde{P}}
\newcommand{\tdQ}{\tilde{Q}}	\newcommand{\tdR}{\tilde{R}}
\newcommand{\tdS}{\tilde{S}}	\newcommand{\tdT}{\tilde{T}}
\newcommand{\tdU}{\tilde{U}}	\newcommand{\tdV}{\tilde{V}}
\newcommand{\tdW}{\tilde{W}}	\newcommand{\tdX}{\tilde{X}}
\newcommand{\tdY}{\tilde{Y}}	\newcommand{\tdZ}{\tilde{Z}}
%Small Letters
\newcommand{\tda}{\tilde{a}}	\newcommand{\tdb}{\tilde{b}}
\newcommand{\tdc}{\tilde{c}}	\newcommand{\tdd}{\tilde{d}}
\newcommand{\tde}{\tilde{e}}	\newcommand{\tdf}{\tilde{f}}
\newcommand{\tdg}{\tilde{g}}	\newcommand{\tdh}{\tilde{h}}
\newcommand{\tdi}{\tilde{i}}	\newcommand{\tdj}{\tilde{j}}
\newcommand{\tdk}{\tilde{k}}	\newcommand{\tdl}{\tilde{l}}
\newcommand{\tdm}{\tilde{m}}	\newcommand{\tdn}{\tilde{n}}
\newcommand{\tdo}{\tilde{o}}	\newcommand{\tdp}{\tilde{p}}
\newcommand{\tdq}{\tilde{q}}	\newcommand{\tdr}{\tilde{r}}
\newcommand{\tds}{\tilde{s}}	\newcommand{\tdt}{\tilde{t}}
\newcommand{\tdu}{\tilde{u}}	\newcommand{\tdv}{\tilde{v}}
\newcommand{\tdw}{\tilde{w}}	\newcommand{\tdx}{\tilde{x}}
\newcommand{\tdy}{\tilde{y}}	\newcommand{\tdz}{\tilde{z}}

%---------------------------------------
% Vec
%---------------------------------------

%Captital Letters
\newcommand{\vA}{\vec{A}}	\newcommand{\vB}{\vec{B}}
\newcommand{\vC}{\vec{C}}	\newcommand{\vD}{\vec{D}}
\newcommand{\vE}{\vec{E}}	\newcommand{\vF}{\vec{F}}
\newcommand{\vG}{\vec{G}}	\newcommand{\vH}{\vec{H}}
\newcommand{\vI}{\vec{I}}	\newcommand{\vJ}{\vec{J}}
\newcommand{\vK}{\vec{K}}	\newcommand{\vL}{\vec{L}}
\newcommand{\vM}{\vec{M}}	\newcommand{\vN}{\vec{N}}
\newcommand{\vO}{\vec{O}}	\newcommand{\vP}{\vec{P}}
\newcommand{\vQ}{\vec{Q}}	\newcommand{\vR}{\vec{R}}
\newcommand{\vS}{\vec{S}}	\newcommand{\vT}{\vec{T}}
\newcommand{\vU}{\vec{U}}	\newcommand{\vV}{\vec{V}}
\newcommand{\vW}{\vec{W}}	\newcommand{\vX}{\vec{X}}
\newcommand{\vY}{\vec{Y}}	\newcommand{\vZ}{\vec{Z}}
%Small Letters
\newcommand{\va}{\vec{a}}	\newcommand{\vb}{\vec{b}}
\newcommand{\vc}{\vec{c}}	\newcommand{\vd}{\vec{d}}
\newcommand{\ve}{\vec{e}}	\newcommand{\vf}{\vec{f}}
\newcommand{\vg}{\vec{g}}	\newcommand{\vh}{\vec{h}}
\newcommand{\vi}{\vec{i}}	\newcommand{\vj}{\vec{j}}
\newcommand{\vk}{\vec{k}}	\newcommand{\vl}{\vec{l}}
\newcommand{\vm}{\vec{m}}	\newcommand{\vn}{\vec{n}}
\newcommand{\vo}{\vec{o}}	\newcommand{\vp}{\vec{p}}
\newcommand{\vq}{\vec{q}}	\newcommand{\vr}{\vec{r}}
\newcommand{\vs}{\vec{s}}	\newcommand{\vt}{\vec{t}}
\newcommand{\vu}{\vec{u}}	\newcommand{\vv}{\vec{v}}
\newcommand{\vw}{\vec{w}}	\newcommand{\vx}{\vec{x}}
\newcommand{\vy}{\vec{y}}	\newcommand{\vz}{\vec{z}}

%---------------------------------------
% Greek Letters:-
%---------------------------------------
\newcommand{\eps}{\epsilon}
\newcommand{\veps}{\varepsilon}
\newcommand{\lm}{\lambda}
\newcommand{\Lm}{\Lambda}
\newcommand{\gm}{\gamma}
\newcommand{\Gm}{\Gamma}
\newcommand{\vph}{\varphi}
\newcommand{\ph}{\phi}
\newcommand{\om}{\omega}
\newcommand{\Om}{\Omega}
\newcommand{\Qed}{\begin{flushright}\qed\end{flushright}}
\newcommand{\del}[2]{\frac{\partial #1}{\partial #2}}
\newcommand{\Del}[3]{\frac{\partial^{#1} #2}{\partial^{#1} #3}}
\newcommand{\deld}[2]{\dfrac{\partial #1}{\partial #2}}
\newcommand{\Deld}[3]{\dfrac{\partial^{#1} #2}{\partial^{#1} #3}}
\newcommand{\uin}{\mathbin{\rotatebox[origin=c]{90}{$\in$}}}
\newcommand{\usubset}{\mathbin{\rotatebox[origin=c]{90}{$\subset$}}}
\newcommand{\lt}{\left}
\newcommand{\rt}{\right}
\newcommand{\exs}{\exists}
\newcommand{\st}{\strut}
\newcommand{\dps}[1]{\displaystyle{#1}}
\newcommand{\mat}[1]{\left[\begin{matrix}#1\end{matrix}\right]}
\newcommand{\subeq}{\subseteq}

$$