# The Persistence of Vision

**Field-Level PII Recovery and Irreversible Redaction in Multi-Vector VLM Retrievers**

Krishna Bhatnagar (Georgia State University) · Prerna Singhal (Independent Researcher)

Preprint — under review at IEEE SaTML 2027.

📄 **[Read the paper (PDF)](persistence-of-vision.pdf)**

Multi-vector vision-language retrievers (ColPali, ColQwen2) store each page as a grid of
per-patch vectors. We show the stored index is a field-level oracle for the personal data
the page carried: a training-free dictionary search recovers names, identity numbers and
dates of birth at 0.994 / 0.804 / 0.794 top-1 from a 200-candidate lineup drawn from a real
6.8×10⁸-name vocabulary, using only the at-rest index and the public encoder.

The leak is holographic — deleting a field's own patches, or a third of the page around
them, leaves recovery at 1.00 — so patch-level redaction and erasure do not reach the index.
A learned reshaping defense reports 1.00 privacy against a non-adaptive attacker and returns
exactly the undefended rate against an adaptive one.

We introduce **Cataract**, an index-time orthogonal projection that destroys rather than
hides the PII-discriminative subspace, certified against linear reconstruction. It holds the
strongest attacker we evaluate to 0.108 linkage while retaining 86% of NDCG@5 on a real
retrieval corpus, at 0.64 ms per page and no added storage.

Code and recorded runs are released with the paper on publication.
