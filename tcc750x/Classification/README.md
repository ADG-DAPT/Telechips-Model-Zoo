# Classification Benchmark
Below is the benchmark data for Classification models running on the TCC750X.
This table allows you to check the performance of each neural network when executed on the N-Dolphin (TCC750X) board.
Additionally, clicking on a neural network name will allow you to download a version formatted for execution on the board.

### Reference Information
- Results of the accuracy is evaluated on ImageNet validation dataset(#50,000).
- Evaluation: Results obtained using the tc-nn-toolkit.
    - FP32 results were measured with the tc-nn-toolkit after converting to the `.enlight` format.
- Inference Time: Measured using the N-Dolphin EVB with Zero padding input image.
- Reference: Links to the original GitHub repository of the neural network model.

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
            <th colspan="2">Compiled NN Information</th>
            <th rowspan="2">Inference Time(msec)</th>
            <th colspan="2">Accuracy</th>
            <th rowspan="2">References</th>
        </tr>
        <tr>
            <th>Weight, Bias Binary Size(MB)</th>
            <th>Command Binary Size(KB)</th>
            <th>FP32</th>
            <th>INT8</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center"><a href="MobileNet/mobileNetv2_10/">MobileNetv2-10</a></td> <!-- Model -->
            <td align="center">ONNX</td> <!-- Framework -->
            <td align="center">ImageNet</td> <!-- Detections/DataSet -->
            <td align="center">224x224x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">4</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">44</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">1.31</td> <!-- Inference Time(msec): EVB -->
            <td align="center">69.842</td> <!-- Evaluation Result: FP32 -->
            <td align="center">68.796</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://github.com/onnx/models/tree/main/validated/vision/classification/mobilenet">GitHub<a></td> <!-- References: Link -->
        </tr>
    </tbody>
</table>

