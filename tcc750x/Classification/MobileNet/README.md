# MobileNet Benchmark on TCC750X

Below is benchmark data for various **MobileNet models** running on the **TCC750X (N-Dolphin)** platform.  
MobileNet is a family of lightweight and efficient convolutional neural networks optimized for **image classification** tasks, especially on **embedded and mobile devices**.  
<!-- This benchmark showcases how different MobileNet variants (e.g., V1, V2, V3) perform when compiled, quantized (INT8), and executed on the TCC750X board. -->

All models are evaluated using the **ImageNet validation dataset** and compiled with the **tc-nn-toolkit**.  
You can click each model name in the table to download the binary ready for deployment on the device.

---

### 📊 How to Read the Table Below

| Column                    | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Model**                | Name of the neural network model (clickable for download, if available)     |
| **Framework**            | Deep learning framework used (e.g., PyTorch, TFLite, ONNX)                  |
| **Dataset**              | Evaluation dataset used (e.g., ImageNet validation set with 50,000 images)  |
| **Input Size (WxHxC)**   | Model input resolution and channel configuration                            |
| **Quantization Bit**     | Bit-depth used for quantization (e.g., INT8)                                |
| **Binary Files Info.**   | Size of the compiled neural network binaries for TCC750X                    |
| **Inference Time (ms)**  | Measured on the N-Dolphin EVB using zero-padded input images                |
| **Accuracy**             | Classification top-1 accuracy on ImageNet validation dataset (50,000 images)                    |
| **References**           | Link to the original GitHub repository of the model      

- - -
<!--
아래는 TCC750X에서 실행되는 Classification 모델의 벤치마크 자료입니다.
이 표를 통해 각 신경망이 N-Dolphin (TCC750X) 보드에서 실행될 때의 성능을 확인할 수 있습니다.
또한, 신경망 이름을 클릭하면 해당 보드에서 실행할 수 있는 형식의 결과물을 다운로드할 수 있습니다.

참조사항
Evaluation: tc-nn-toolkit을 이용하여 측정한 결과입니다.
- Evaluation Result의 FP32: .enlight 확장자로 변환된 상태에서 측정된 값입니다.
Inference Time: N-Dolphin EVB에서 실행한 결과입니다.
Reference: 신경망 모델의 원본 GitHub 링크로 연결됩니다.
-->

<table border="1" cellspacing="0" cellpadding="5">
    <thead>
        <tr>
            <th rowspan="2">Model</th>
            <th rowspan="2">Framework</th>
            <th rowspan="2">DataSet</th>
            <th rowspan="2">Input Size (WxHxC)</th>
            <th rowspan="2">Quantization Bit</th>
            <th colspan="2">Binary Files Info.</th>
            <th rowspan="2">Inference Time(ms)</th>
            <th colspan="2">Accuracy</th>
            <th rowspan="2">References</th>
        </tr>
        <tr>
            <th>Weight & Bias Bin.(MB)</th>
            <th>Command Bin.(KB)</th>
            <th>FP32</th>
            <th>INT8</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center"><a href="mobileNetv2_10/">MobileNetv2-10</a></td> <!-- Model -->
            <td align="center">MXNet</td> <!-- Framework -->
            <td align="center">ImageNet</td> <!-- Detections/DataSet -->
            <td align="center">224x224x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">4</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">44</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">1.31</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.6984</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.6879</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://github.com/onnx/models/tree/main/validated/vision/classification/mobilenet">GitHub<a></td> <!-- References: Link -->
        </tr>
    </tbody>
</table>

- - -

## 📤 Output Format

- The output is a 1D tensor of **1000 class scores** (ImageNet classes).
- Apply **softmax** to obtain class probabilities.
- Return the top-k predicted class indices and confidence scores.

- - -

## 🔗 Official Resources
- 💻 [MobileNet ONNX Github](https://github.com/onnx/models/tree/main/validated/vision/classification/mobilenet)
- 📜 [MobileNet Paper](https://arxiv.org/abs/1801.04381)