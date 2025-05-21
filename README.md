
下载环境
```
conda activate yes

conda create --name yes python=3.8
```

1.启动虚拟环境

```
conda activate yes
```

2.打开图像识别

```
labelImg
```

安装PyTorch
```
pip install torch==2.0.0+cu118 torchvision==0.15.1+cu118 torchaudio==2.0.1+cu118 -f https://download.pytorch.org/whl/torch_stable.html
```

安装opancv
```
pip install torch torchvision opencv-python
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

打开串口
```
pip install pyserial

python serial_example.py

python send.py

python receive.py

python detect.py
```

创建文件夹
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

