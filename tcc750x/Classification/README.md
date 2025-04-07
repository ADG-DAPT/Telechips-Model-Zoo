# Classification Benchmark on TCC750x
The following is benchmark data for various image classification models running on the **TCC750x** platform.  
The following table allows you to compare the performance of each neural network when running on the TCC750x.  
You can also click the model name to download the version formatted for execution on the TCC750x.

- - -

### 📊 Table Overview

| Column                    | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Model**                | Name of the neural network model (clickable for download, if available)     |
| **Framework**            | Deep learning framework used (e.g., PyTorch, TFLite, ONNX)                  |
| **Dataset**              | Evaluation dataset  |
| **Input Size (WxHxC)**   | Model input resolution and channel configuration                            |
| **Quantization Bit**     | Bit-depth used for quantization (e.g., INT8)                                |
| **Binary Files Information**   | Size of the compiled neural network binaries for TCC750x                    |
| **Inference Time (ms)**  | Inference time measured on the TCC750x EVB using zero-padded input images                |
| **Accuracy**             | Classification top-1 accuracy on the ImageNet validation dataset (50,000 images)                    |
| **References**           | Link to the original GitHub repository of the model      

- - -

<table border="1" cellspacing="0" cellpadding="5">
    <thead>
        <tr>
            <th rowspan="2">Model</th>
            <th rowspan="2">Framework</th>
            <th rowspan="2">DataSet</th>
            <th rowspan="2">Input Size (WxHxC)</th>
            <th rowspan="2">Quantization Bit</th>
            <th colspan="2">Binary Files Information</th>
            <th rowspan="2">Inference Time (ms)</th>
            <th colspan="2">Accuracy</th>
            <th rowspan="2">References</th>
        </tr>
        <tr>
            <th>Weight and Bias Binary (MB)</th>
            <th>Command Binary (KB)</th>
            <th>FP32</th>
            <th>INT8</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center"><a href="MobileNet/mobileNetv2_10/">mobileNetv2-10</a></td> <!-- Model -->
            <td align="center">MXNet</td> <!-- Framework -->
            <td align="center">ImageNet</td> <!-- Detections/DataSet -->
            <td align="center">224x224x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">4</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">44</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">1.24</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.6984</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.6879</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://github.com/onnx/models/tree/main/validated/vision/classification/mobilenet">GitHub<a></td> <!-- References: Link -->
        </tr>
    </tbody>
</table>

