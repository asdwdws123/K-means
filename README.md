# K-means
K-means 是一种广泛使用的聚类算法，主要用于将数据划分为 \(K\) 个集群。这个算法的主要逻辑可以概括为以下几个步骤：

1. **初始化**：随机选择 \(K\) 个数据点作为初始的聚类中心。
2. **分配**：对于每一个数据点，计算它与每个聚类中心的距离，并将其分配到最近的聚类中心所代表的集群。
3. **更新**：对于每个集群，重新计算该集群所有点的平均值，并将该平均值作为新的聚类中心。
4. **重复**：重复步骤 2 和步骤 3，直到聚类中心不再发生变化，或者达到预设的迭代次数。

这个过程可以通过以下公式来描述：

- **分配步骤**：给定数据点 \(x_i\)，找到距离 \(x_i\) 最近的聚类中心 \(c_j\)，则 \(x_i\) 被分配到聚类 \(j\)。这里的距离通常使用欧氏距离来计算，即：

\[\text{dist}(x_i, c_j) = \sqrt{\sum_{k=1}^{n} (x_{ik} - c_{jk})^2}\]

其中，\(n\) 是数据点的维度。

- **更新步骤**：对于每个聚类 \(j\)，新的聚类中心 \(c_j'\) 是聚类中所有点的均值，计算公式为：

\[
c_j' = \frac{1}{|S_j|} \sum_{x_i \in S_j} x_i
\]

其中，\(S_j\) 是分配给聚类中心 \(c_j\) 的所有数据点的集合，\(|S_j|\) 是该集合中数据点的数量。

K-means 算法的目标是最小化所有集群中的总内部平方误差（SSE），即：

\[
\text{SSE} = \sum_{j=1}^{K} \sum_{x_i \in S_j} \text{dist}^2(x_i, c_j)
\]

该算法简单而高效，适用于大量数据集的聚类分析。然而，它也有一些局限性，如对初始聚类中心的选择敏感，可能会陷入局部最优，且需要预先指定 \(K\) 值。
