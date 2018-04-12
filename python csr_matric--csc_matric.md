# **python csr_matric--csc_matric**

## csr_matric 和csc_matric的使用是因为在用Python进行科学运算时，常常需要把一个稀疏的np.array进行压缩,这时候就用到scipy库中sparse.csr_matrix(csr:Compressed Sparse Row marix) 

## 和sparse.csc_matric(csc:Compressed Sparse Column marix)

## csc_matric是稀疏矩阵按列存储Compressed Sparse Colum (CSC)存储原理

## csr_matric是稀疏矩阵按行存储Compressed Sparse Row (CSR)存储原理

![1](/home/truthliu/Desktop/1.png)

## indptr=[0,2,4,7,9]

## indices=[0,1,1,2,0,2,3,1,3]

## data=[1,7,2,8,5,3,9,6,4]

## 我们可以根据上图看出一些端倪，就是indptr的最后一个数字是我们这个矩阵中所存储的元素个数，而前面的几个数字是我们每一行的第一个非零元素所在data那个数组中对应的下标，我们可以根据这个来确定每一行中，每个开始元素的值，然后我们在观察indices这个数组，网上许多说的含糊不清，其实这个indice数组所存的就是每个非零元素列的下标值，可以根据这个来确定我们的每一行中其他元素所在位置，就是上图中左边的那个Matric矩阵。

## 步骤如下：

## 1、根据indptr确定元素所在data中的位置，可以直接划分每一行中有多少个非零元素，根据indptr中元素对应的data数组下标进行了划分：（1,7）（2,8）（5,3,9）(6,4）

## 2、然后我们根据indices中列的下标来确定每个data的位置，将data数据写入到Matric中即可。



## 