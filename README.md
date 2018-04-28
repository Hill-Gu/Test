# py-faster-rcnn
## 下载py-faster-rcnn源代码
`git clone –recursive https://github.com/rbgirshick/py-faster-rcnn.git`
## 编译caffe
### 安装依赖项
- cython
- easydict
- opencv
### 编译cython模块
```
cd py-faster-rcnn/lib
make
```
### 编译caffe和pycaffe
```
cd caffe-fast-rcnn
cp Makefile.config.example Makefile.config
gedit Makefile.config
```
修改下列部分：
1. # USE_CUDNN = 1
2. WITH_PYTHON_LAYER = 1
3. INCLUDE_DIRS := $(PYTHON_INCLUDE) /usr/local/include后面打上一个空格 然后添加/usr/include/hdf5/serial如果没有这一句可能会报一个找不到hdf5.h的错误
4. 
然后编译：
```
make all -j128
make test -j128
make runtest -j128
make pycaffe -j128
```
