Changelog
=========

[0.2.0] - Feb 11, 2020
----------------------

Changed
~~~~~~~

- The default value of ``optimal_ordering`` is changed to ``False`` in
  ``cluster.MIRAC``.

Added
~~~~~

- Support to sparse matrix in core data structures, including
  ``eda.SampleDistanceMatrix``, ``eda.SampleFeatureMatrix``,
  ``eda.SingleLabelClassifiedSamples``, and
  ``eda.MDLSingleLabelClassifiedSamples``.

- Option to avoid pairwise distance computation in ``eda.SampleDistanceMatrix``
  constructor by specifying ``use_pdist=False``.

- Community clustering, ``cluster.Community``.

- Community detection extended MIRAC clustering, ``cluster.CommunityMIRAC``.

- Option to build k nearest neighbor graph with approximate nearest neighbor
  (ANN) search using Hierarchical Navigable Small World (HNSW) graph, in
  ``eda.SampleDistanceMatrix.s_knn_graph``.

- Support to Python 3.7.


[0.1.7] - Jul 2, 2019
---------------------

Changed
~~~~~~~

- Fixed ``sdm.SampleDistanceMatrix.umap``. Pass parameters to the ``UMAP``
  function call.

[0.1.6] - Jan 2, 2019
---------------------

Added
~~~~~

- Changelog to keep track of changes in each update.

Changed
~~~~~~~

- Renamed ``qc`` module to ``knn``, in accordance with the updated manuscript.
  This change clarifies the meaning of 'quality control' in this package, which
  is different from its typical meaning. In this package, quality control means
  to *explore the data according to certain qualities of samples and features*,
  rather than filtering the raw data according to technical parameters
  determined by domain specific knowledge.

- Renamed ``qc.SampleKNNFilter`` to ``knn.RareSampleDetection``, in accordance
  with the updated manuscript. This change clarifies the purpose of this
  procedure, which is to identify samples distinct from their nearest neighbors
  *for further inspection rather than removal*. Filtering usually refers to the
  removal of samples.

- Renamed ``qc.FeatureKNNPickUp`` to ``knn.FeatureImputation``, in accordance
  with the updated manuscript. This change clarifies the purpose of this
  procedure in the field of single-cell RNA-seq data analysis, which is to
  reasonably change zero entries in the data matrix into non-zero entries. This
  procedure is usually called 'imputation' in the field of single-cell RNA-seq
  data analysis.

- Moved ``qc.remove_constant_features`` to ``utils.remove_constant_features``.
