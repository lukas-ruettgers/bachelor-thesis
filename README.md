# Abstract
The reasonable maximum demand on out-of-distribution generalization is that the learning algorithm should infer the *simplest* function that remains consistent with the observed data.
Kolmogorov complexity intuitively formalizes the notion of simplicity from an information-theoretic viewpoint, as it associates the simplicity of a function with the description length of the shortest program that can compute it.
In light of this descriptive complexity, this thesis addresses limitations in our model classes, optimization techniques, and statistical learnability conditions that impede learning simple functions.

Firstly, it demonstrates that models with a *non-recursive structure* such as finite-precision feed-forward neural networks are incapable of even expressing a class of functions that yet preserve a constantly low Kolmogorov complexity.
On the other extreme, models that allowed to express *any partial computable function* would render learnability from finite datasets practically impossible with standard learning algorithms.
This is because present learnability conditions in theory either restrict themselves to exemplary model or hypothesis classes [[1]](#1),[[2]](#2), or rely on overly conservative assumptions such as the ubiquitous *i.i.d.* assumption [[3]](#3),[[4]](#4).

In this setting of overarching model expressivity, this work instead substantiates how incorporating Kolmogorov complexity as a simplicity bias into the optimization objective function carves the way to formulate general distribution-free, both necessary and sufficient information-theoretic conditions that a dataset must satisfy to learn *any* partial computable function, and exemplifies how such an inductive bias can further reduce the sample size that is usually required for classical learnability guarantees.
To that end, it proposes to directly draw upon Kolmogorov complexity to quantify the information that finite datasets convey about the functions that could have possibly generated it.

Because Kolmogorov complexity is incomputable in general, compression algorithms are typically proposed as viable approximations [[5]](#5). 
However, for *any* choice on the encoding of Turing Machines, contemporarily employed compression algorithms such as the Lempel-Ziv-Welch compression can not even yield approximate guarantees about the order between the Kolmogorov complexity of two binary strings, because such compression algorithms do not keep up with the compression power of Turing Machines.

## References
<a id="1">[1]</a>
K. Ahuja, E. Caballero, D. Zhang, J.-C. Gagnon-Audet, Y. Bengio, I. Mitliagkas,
and I. Rish.
Invariance principle meets information bottleneck for out-of-distribution
generalization. 
Advances in Neural Information Processing Systems, vol. 34, pp. 3438-3450, 2021.

<a id="2">[2]</a>
M. Arjovsky, L. Bottou, I. Gulrajani, and D. Lopez-Paz. 
Invariant risk minimization.
arXiv preprint arXiv:1907.02893, 2019.

<a id="3">[3]</a>
D. Paccagnan, M. Campi, and S. Garatti.
The pick-to-learn algorithm: Empowering compression for tight generalization bounds and improved post-training performance.
Advances in Neural Information Processing Systems, vol. 36, 2024.

<a id="4">[4]</a>
M. C. Campi and S. Garatti.
Compression, generalization and learning.
Journal of Machine Learning Research, vol. 24, no. 339, pp. 1-74, 2023.

<a id="5">[5]</a>
R. Cilibrasi and P. M. Vitányi.
Clustering by compression. 
IEEE Transactions on Information theory, vol. 51, no. 4, pp. 1523-1545, 2005.
