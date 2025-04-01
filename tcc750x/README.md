# TCC750x

![N-Dolphin Image](../docs/image/n_dolphin.png)

This folder contains benchmark data for neural networks supported by the TCC750x, as well as neural network models that can be run on the TCC750x EVB.

TCC750x - [Classification](./Classification/README.md), [Object_detection](./Object_detection/README.md)

---

## **Getting Started**
Follow the steps to run a model on a TCC750x EVB.

### 1. Clone repository:
<pre> <code>
git clone git@github.com:ADG-DAPT/Telechips-Model-Zoo.git
</code> </pre>

### 2. Copy desired model to EVB:
Copy the entire model folder to TCC750x EVB. Each folder contains the necessary output files (.so, .bin, etc.).
<pre> <code>
scp -r [network_output_folder] root@192.168.0.100:/path/to/target/
</code> </pre>
Replace [network_output_folder] with the actual folder (e.g., yolov5m/).  
Replace <evb_ip> with the IP address of TCC750x EVB.

### ***Example: TCC750x - YOLOv5m Folder Structure***
<pre> <code>
yolov5m_quantized/
├── net.so        # Compiled model library
├── npu_cmd.bin       # Binary file of TCC750x NPU command code word
└── quantized_network.bin # Binary file of Quantized weight and bias 
</code> </pre>
then run:
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
