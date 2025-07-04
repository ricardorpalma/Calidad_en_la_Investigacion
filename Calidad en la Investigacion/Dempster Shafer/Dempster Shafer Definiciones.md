
Aleatory an Epsistemic Uncertainly

**Aleatoric Uncertainty:** This is the uncertainty of the process which you are trying to model. Say, you want to train a model with some sensor output where the sensor is itself producing some random fluctuations in its reading. So, no matter how many data points you take, your model will not be able to reduce that uncertainty, as the data itself has uncertainty in it. So, aleatoric uncertainty is the **uncertainty in data**.

**Epistemic Uncertainty:** This uncertainty happens for lack of enough data to estimate the model parameters properly. If you add more data, this uncertainty will be reduced. So, epistemic uncertainty is the **uncertainty in model parameters**.

### Otro Ejemplo

**Aleatoric:** uncertainty about the result of an experiment that we can repeat, e.g. dice roll. What is the probability of rolling a 6? - the view of _frequency statistics_

**Epistemic:** uncertainty stemming from insufficient knowledge, e.g. one-time experiment (no repeating). What is the probability that - as a result of global warming - the average temperature will be 2 degrees higher in 2050?



## Example 2


https://www.scaler.com/topics/artificial-intelligence-tutorial/dempster-shafer-theory-in-artificial-intelligence/

Consideremos dos posibles apuestas
La primera apuesta es que, al lanzar una moneda que sabemos que es justa, saldrá cara. Ahora consideremos la segunda apuesta, en la que apostamos al resultado de una pelea entre el mejor boxeador y el mejor luchador del mundo. Supongamos que somos bastante ignorantes en artes marciales y que tendríamos grandes dificultades para elegir a quién apostar.

Muchas personas se sentirían más inseguras al hacer la segunda apuesta, en la que las probabilidades son desconocidas, que la primera, en la que es fácil ver que las probabilidades son la mitad para cada resultado. La teoría de Dempster-Shafer permite considerar la confianza que uno tiene en las probabilidades asignadas a los diversos resultados.


## Formalismo



[[edit](https://en.wikibooks.org/w/index.php?title=Expert_Systems/Dempster-Shafer_Theory&veaction=edit&section=3 "Edit section: Formalism") | [edit source](https://en.wikibooks.org/w/index.php?title=Expert_Systems/Dempster-Shafer_Theory&action=edit&section=3 "Edit section's source code: Formalism")]

Let _X_ be the _universal set_: the set of all states under consideration. The power set, P(X)![{\displaystyle \mathbb {P} (X)\,\!}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8f87895486d57ec27ad5208665a4d4e98510865d), is the set of all possible sub-sets of _X_, including the empty set. For example, if:

X={a,b}![{\displaystyle X=\left\{a,b\right\}\,\!}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a2cfba73e9b3c35c46ddb544b02f0c441d7e22c9)

then

P(X)={∅,{a},{b},X}.![{\displaystyle \mathbb {P} (X)=\left\{\varnothing ,\left\{a\right\},\left\{b\right\},X\right\}.\,\!}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bf9b75bd5494ceffcdca020be5c6f2209c1cb944)

The elements of the power set can be taken to represent propositions that one might be interested in, by containing all and only the states in which this proposition is true.

The theory of evidence assigns a belief mass to each subset of the power set. Formally, a function m:P(X)→[0,1]![{\displaystyle m:\mathbb {P} (X)\rightarrow [0,1]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/70ef24acf8bb2dd192a8692746e8bca16af8f937), is called a _basic belief assignment_ (BBA), when it verifies two axioms. First, the mass of the empty set is zero:

m(∅)=0.![{\displaystyle m(\varnothing )=0.\,\!}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f25921caaa169e9bbb782820fd2ab0b7f1285e8b)

Second, the masses of the remaining members of the power set add up to a total of 1:

1=∑A∈P(X)m(A).![{\displaystyle 1=\sum _{A\in \mathbb {P} (X)}m(A).\,\!}](https://wikimedia.org/api/rest_v1/media/math/render/svg/213fa8ed4ae119b3669061c9200476df4563d0ad)

The mass _m_(_A_) of a given member of the power set, _A_, expresses the proportion of all relevant and available evidence that supports the claim that the actual state belongs to _A_ but to no particular subset of _A_. The value of _m_(_A_) pertains _only_ to the set _A_ and makes no additional claims about any subsets of _A_, each of which has, by definition, its own mass.

From the mass assignments, the upper and lower bounds of a probability interval can be defined. This interval contains the precise probability of a set of interest (in the classical sense), and is bounded by two non-additive continuous measures called **belief** (or **support**) and **plausibility**:

bel⁡(A)≤P(A)≤pl⁡(A).![{\displaystyle \operatorname {bel} (A)\leq P(A)\leq \operatorname {pl} (A).\,\!}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1ddc78121b999a265dddf1242f998b4784105d32)

The belief bel(_A_) for a set _A_ is defined as the sum of all the masses of (not necessarily proper) subsets of the set of interest:

bel⁡(A)=∑B∣B⊆Am(B).![{\displaystyle \operatorname {bel} (A)=\sum _{B\mid B\subseteq A}m(B).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7a546521148d76f640dc7dc6866ec03b041a6530)

The plausibility pl(_A_) is the sum of all the masses of the sets _B_ that intersect the set of interest _A_:

pl⁡(A)=∑B∣B∩A≠∅m(B).![{\displaystyle \operatorname {pl} (A)=\sum _{B\mid B\cap A\neq \varnothing }m(B).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/108664a761af36a2e9789f4a96ca4b3c72e08913)

The two measures are related to each other as follows:

pl⁡(A)=1−bel⁡(A¯).![{\displaystyle \operatorname {pl} (A)=1-\operatorname {bel} ({\overline {A}}).\,\!}](https://wikimedia.org/api/rest_v1/media/math/render/svg/afea87888cbb0081f3c4b4aac798d833947f129a)

It follows from the above that you need know but one of the three (mass, belief, or plausibility) to deduce the other two, though you may need to know the values for many sets in order to calculate one of the other values for a particular set.


