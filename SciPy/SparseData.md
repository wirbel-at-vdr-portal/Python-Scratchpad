[back to index](Index.md)

# Sparse Data

[scipy.sparse](https://docs.scipy.org/doc/scipy/reference/sparse.html) is a **2-D sparse array** package for numeric data.

* **Sparse data** is data that has mostly unused elements (elements that don't carry any information).  
It can be an array like this one: [1, 0, 2, 0, 0, 3, 0, 0, 0, 0, 0, 0]

There are seven available sparse matrix types:
* **csc_matrix**: Compressed Sparse Column format
* **csr_matrix**: Compressed Sparse Row format
* **bsr_matrix**: Block Sparse Row format
* **lil_matrix**: List of Lists format
* **dok_matrix**: Dictionary of Keys format
* **coo_matrix**: COOrdinate format (aka IJV, triplet format)
* **dia_matrix**: DIAgonal format

There are primarily two types of sparse matrices that we use:
* CSC - Compressed Sparse Column. For efficient arithmetic, fast column slicing.
* CSR - Compressed Sparse Row. For fast row slicing, faster matrix vector products

```
import numpy as np
from scipy.sparse import csr_matrix

arr = np.array([0, 0, 0, 0, 0, 1, 1, 0, 2])

print(csr_matrix(arr))
#  (0, 5)	1
#  (0, 6)	1
#  (0, 8)	2
```
> [!NOTE]
> The print command shows only the zero-based 2D-indices with for non-zero values.

The data property shows the stored data.
```
print(csr_matrix(arr).data)
[1 1 2]
```












[back to index](Index.md)
