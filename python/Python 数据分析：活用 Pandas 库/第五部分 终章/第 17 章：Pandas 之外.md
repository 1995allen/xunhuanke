<!-- code_chunk_output -->

# 17.1 科学计算栈

- NumPy
  - 数值计算始于1995年，2006年发展成了 NumPy 库
  - NumPy 库是本书使用的 Pandas Series 对象的基础
&nbsp;

- Matplotlib
  - 创建于2002年
  - 也是 Pandas 使用的绘图方法
&nbsp;

- Pandas
  - 处理异构数据的能力很强大
  - 使得分析人员能使用 scikit 清理各类数据，便于后续分析
  - 2000 年， scikit 基于 SciPy 包创建而来

# 17.2 性能

> 过早优化是万恶之源

- SciPy 生态系统提供了 cython 库和 numba 库，它们能加速 Python 运行

## 17.2.1 测试代码运行时间

- IPython 还提供了很多“魔法指令”，为 Python 带来了更多特性，进一步增强了 Python 的性能
  - 示例运用了装饰器，不太懂，略过

## 17.2.2 分析代码

- cProfile snakevis 工具有助于计算整个脚本和代码块的运行时间，并逐行列出执行情况

# 17.3 规模更大、速度更快

- concurrent.futures 允许将函数调用重写为内置的 map 函数
- Dask 库也可以用于处理大型数据集
  - 他允许创建计算图
  - 其中只有“过时”的计算才需要重新计算
  - 语法与 Pandas 相同
