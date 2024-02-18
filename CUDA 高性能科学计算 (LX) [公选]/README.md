# CUDA 高性能科学计算 [公选]

（虽说是公选课，但是也一起放上来吧）

- 选题：使用 CUDA 并行实现 K-Means 聚类算法对图像进行聚类
- 串行实现：`KMeans.zip`
- CUDA 并行实现：`KMeans-CUDA.zip`

压缩包内不包含测试图片，请自行选取。`coverter.py` 用于将图片转为整型矩阵供 C 读取。

#### 串行版本

```
==========================================
Enter image file name: ../../diona.txt
Enter number of clusters: 20
Enter number of rounds: 100
Loading image
Finished! Image size: 1364x1364
Execution time: 2.98s
Init center
Finished! Execution time: 0.11s
Running K-means
Round:  100/100 Execution time:   207ms
Finished! Execution time: 20.93s
Saving result to result.txt
Finished! Execution time: 2.22s
==========================================
Enter image file name: ../../klee.txt
Enter number of clusters: 20
Enter number of rounds: 100
Loading image
Finished! Image size: 7175x3484
Execution time: 54.36s
Init center
Finished! Execution time: 2.74s
Running K-means
Round:  100/100 Execution time:  2786ms
Finished! Execution time: 321.13s
Saving result to result.txt
Finished! Execution time: 29.15s
==========================================
Enter image file name: ../../nahida.txt
Enter number of clusters: 20
Enter number of rounds: 100
Loading image
Finished! Image size: 10240x4320
Execution time: 117.04s
Init center
Finished! Execution time: 7.67s
Running K-means
Round:  100/100 Execution time:  5006ms
Finished! Execution time: 511.55s
Saving result to result.txt
Finished! Execution time: 51.83s
==========================================
```

#### 并行版本

```
==========================================
Device ID: 0    Number of SMs: 46
Enter image file name: ../../diona.txt
Enter number of clusters: 20
Enter number of rounds: 100
Loading image
Finished! Image size: 1364x1364
Execution time: 3.18s
Init center
Finished! Execution time: 0.11s
Running K-means
Round:   100/100  Execution time:     2ms
Finished! Execution time: 0.27s
Saving result to result.txt
Finished! Execution time: 2.22s
==========================================
Device ID: 0    Number of SMs: 46
Enter image file name: ../../klee.txt
Enter number of clusters: 20
Enter number of rounds: 100
Loading image
Finished! Image size: 7175x3484
Execution time: 47.92s
Init center
Finished! Execution time: 4.09s
Running K-means
Round:   100/100  Execution time:    26ms
Finished! Execution time: 3.42s
Saving result to result.txt
Finished! Execution time: 66.89s
==========================================
Device ID: 0    Number of SMs: 46
Enter image file name: ../../nahida.txt
Enter number of clusters: 20
Enter number of rounds: 100
Loading image
Finished! Image size: 10240x4320
Execution time: 75.42s
Init center
Finished! Execution time: 5.17s
Running K-means
Round:   100/100  Execution time:    49ms
Finished! Execution time: 5.48s
Saving result to result.txt
Finished! Execution time: 54.27s
==========================================
```

