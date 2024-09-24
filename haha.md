# 封闭流形 Mesh

## 定义
给定一个流形 \( G(V,E,F) \)，其中：

- \( V = \{v_0, v_1, \ldots, v_{499}\} \)

### 欧拉定律
根据欧拉定律：

\[
\text{num}(V) - \text{num}(E) + \text{num}(F) = 2
\]

由此可得：

\[
500 - E + F = 2
\]

### 面的关系
已知每个面有 3 条边：

\[
3F = 2E
\]

因此：

\[
E = 1.5F
\]

### 求解
将 \( E \) 代入欧拉定律：

\[
500 - 1.5F + F = 2 
\]

简化得：

\[
500 - 0.5F = 2 
\]

最终得出：

\[
498 = 0.5F \quad \Rightarrow \quad F = 996
\]
\[
E = 1494
\]

### 结果
得到最终结果：

- \(\text{num}(V) = 500\)
- \(\text{num}(F) = 996\)
- \(\text{num}(E) = 1494\)

## 待求解的集合
- 边集合： \( E_{\text{true}} = \{e_0, e_1, \ldots, e_{1493}\} \)
- 面集合： \( F_{\text{true}} = \{f_0, f_1, \ldots, f_{995}\} \)

### 搜索空间
- 边的搜索空间： \( \text{num}(V) \times \text{num}(V) \) 种情况
- 面的搜索空间： \( \text{num}(V) \times \text{num}(V) \times \text{num}(V) \) 种情况

## 缩小搜索空间
- 初始边集合： \( E_{\text{start}} = \{e_0, e_1, \ldots, e_{\text{num}(V)^2}\} \)
- 尝试集合： 
  - \( E_{\text{try}_1} = \sigma_1[E_{\text{start}}] \)
  - \( E_{\text{try}_2} = \sigma_2[E_{\text{try}_1}] \)
  - \( E_{\text{try}_3} = \sigma_3[E_{\text{try}_2}] \)

  依此类推：

\[
E_{\text{try}_n} = \sigma_n[\sigma_{n-1}[\sigma_{n-2}[\ldots[\sigma_2[\sigma_1[E_{\text{start}}]]]]]]
\]

### 采样搜索空间
- 采样结果：

\[
E_{\text{sample}_1} = \text{Sample}(E_{\text{try}_n, \text{num}(E)})
\]
