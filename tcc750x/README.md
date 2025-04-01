# TCC750x

![N-Dolphin Image](../docs/image/n_dolphin.png)

This folder contains benchmark data for neural networks supported by the TCC750x, as well as neural network models that can be run on the board.

<!--
이 폴더에는 TCC750X에서 지원하는 신경망의 벤치마크 자료와 보드에서 실행할 수 있는 신경망 모델이 포함되어 있습니다.
-->

TCC750x - [Classification](./Classification/README.md), [Object_detection](./Object_detection/README.md)

---

## **Getting Started**
Follow the steps to run a model on a Telechips Evaluation Board (EVB).

### 1. Clone the repository:
<pre> <code>
git clone git@github.com:ADG-DAPT/Telechips-Model-Zoo.git
</code> </pre>

### 2. Copy the desired model to the EVB:
Copy the entire model folder to your EVB. Each folder contains the necessary output files, including .so and .bin.
<pre> <code>
scp -r [network_output_folder] root@192.168.0.100:/path/to/target/
</code> </pre>
Replace [network_output_folder] with the actual folder (For example, yolov5m/).
Replace <evb_ip> with the IP address of your EVB board.

### ***Example: TCC750x - YOLOv5m Folder Structure***
<pre> <code>
yolov5m_quantized/
├── net.so        # Compiled model library
├── npu_cmd.bin       # Binary file of TCC750x NPU command code word
└── quantized_network.bin # Binary file of Quantized weight and bias 
</code> </pre>
So you would run:
<pre> <code>
scp -r yolov5m_quantized/ root@192.168.0.100:/home/root/
</code> </pre>

### 3. Run the model using tcnputestapp or tcnnapp:
<pre> <code>
tcnputestapp -d 0 1 -n [network_output_folder_path]
</code> </pre>
or
<pre> <code>
tcnnapp -n [network_output_folder_path]
</code> </pre>
