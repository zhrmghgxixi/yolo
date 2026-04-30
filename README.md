
# 下载环境

## yolo26
新建一个环境：
```
conda create --name py38yolo26 python=3.8 -y
```

进入环境：
```
conda activate py38yolo26
```

检查 Python 版本：
```
python --version
```

正常应该显示：Python 3.8.x

3. 安装 PyTorch + CUDA 11.8

你之前 YOLOv8 用的是 CUDA 11.8，所以这里继续用 CUDA 11.8：
```
conda install pytorch==2.0.0 torchvision==0.15.0 torchaudio==2.0.0 pytorch-cuda=11.8 -c pytorch -c nvidia -y
```

安装完成后检查 GPU 是否可用：
```
python -c "import torch; print(torch.__version__); print(torch.cuda.is_available()); print(torch.version.cuda)"
```

正常结果应该类似：
2.0.0
True
11.8

如果显示：False,说明 PyTorch 没有调用到显卡，需要检查显卡驱动或 CUDA 版 PyTorch 是否安装正确。

4. 安装 OpenCV
```
conda install -c conda-forge opencv -y
```

检查 OpenCV：
```
python -c "import cv2; print(cv2.__version__)"
```

5. 安装 labelImg,如果你还要继续标注图片，就安装：
```
conda install -c conda-forge labelimg -y
```

启动测试：
```
labelImg
```

6. 安装 Ultralytics,优先使用官方源：
```
python -m pip install -U ultralytics
```

如果下载慢，可以用清华源：
```
python -m pip install -U ultralytics -i https://pypi.tuna.tsinghua.edu.cn/simple
```

如果你想继续用阿里源，也可以：
```
python -m pip install -U ultralytics -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com --timeout 120 --retries 10
```

安装后检查版本：
```
python -c "import ultralytics; print(ultralytics.__version__)"
```

检查 YOLO 环境：
```
yolo checks
```

7. 测试 YOLO26 是否能加载,执行：
```
python -c "from ultralytics import YOLO; model=YOLO('yolo26s.pt'); print('YOLO26s加载成功')"
```

第一次运行时，如果本地没有 yolo26s.pt，它会自动下载。

也可以测试推理：
```
yolo detect predict model=yolo26s.pt source=C:/Users/Lenovo/Desktop/test.jpg device=0
```
如果网络图片下载失败，就用本地图片：
```
yolo detect predict model=yolo26s.pt source=https://ultralytics.com/images/bus.jpg device=0
```

假设你的数据集配置文件是：

C:/Users/Lenovo/Desktop/my_dataset/data.yaml

那么训练命令用这个：
```
yolo detect train model=yolo26s.pt data=C:/Users/Lenovo/Desktop/my_dataset/data.yaml epochs=100 imgsz=640 batch=4 device
```


## yolov8
```
conda create --name py38yolo8 python=3.8

conda activate py38yolo8

conda install -c conda-forge labelimg -y
```

1.启动、退出虚拟环境

```
conda activate py38yolo8

conda deactivate
```

2.打开图像识别

```
labelImg
```

安装PyTorch
```
conda install pytorch==2.0.0 torchvision==0.15.0 torchaudio==2.0.0 pytorch-cuda=11.8 -c pytorch -c nvidia -y
```

安装opancv
```
conda install -c conda-forge opencv -y
```

安装ultralytics
```
python -m pip install ultralytics -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com
```

运行
```
python detect.py
```

检查Gpu
```

python

import torch

torch.__version__

torch.cuda.is_available() 

exit()
```

3.跑模型

```
yolo task=detect mode=train epochs=100 data=D:/images/data_custom.yaml model=yolov8s.pt imgsz=640

yolo task=detect mode=train epochs=100 data=./data_custom.yaml model=yolov8s.pt imgsz=640
```

4.测试

```
yolo task=detect mode=predict model=yolov8s_custom.pt show=True conf=0.5 source=1.jpeg

yolo task=detect mode=predict model=yolov8s_custom.pt show=True conf=0.5 source=1.mp4
```

5.改名字
```
yolov8s_custom.pt
```




# Conda指令：
看当前在哪个环境
```
conda info --envs
```

# 打开串口
```
pip install pyserial

python serial_example.py

python send.py

python receive.py

python detect.py
```

# 创建文件夹
```
mkdir
```

ModuleNotFoundError: No module named 'cv2' 错误表示你的 Python 环境中没有安装 OpenCV 库。你可以使用以下命令来安装 OpenCV：
```
pip install opencv-python
```

ModuleNotFoundError: No module named 'ultralytics' 错误表示你的 Python 环境中没有安装 ultralytics 库。你可以使用以下命令来安装 ultralytics 库：
```
pip install ultralytics
```

下位机
```
python detect.py

```

