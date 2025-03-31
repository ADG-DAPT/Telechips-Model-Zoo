# Object Detection Benchmark
Below is the benchmark data for Object Detection models running on the TCC750X.
This table allows you to check the performance of each neural network when executed on the N-Dolphin (TCC750X) board.
Additionally, clicking on a neural network name will allow you to download a version formatted for execution on the board.

### Reference Information
- Results of the mAP is evaluated on COCO val2017 dataset(#5,000) or VOC2007 test dataset (#4,952).
- Evaluation: Results obtained using the tc-nn-toolkit.
    - FP32 results were measured with the tc-nn-toolkit after converting to the `.enlight` format.
- Inference Time: Measured using the N-Dolphin EVB with Zero padding input image.
- Reference: Links to the original GitHub repository of the neural network model.


<!--
아래는 TCC750X에서 실행되는 Object Detection 모델의 벤치마크 자료입니다.
이 표를 통해 각 신경망이 N-Dolphin (TCC750X) 보드에서 실행될 때의 성능을 확인할 수 있습니다.
또한, 신경망 이름을 클릭하면 해당 보드에서 실행할 수 있는 형식의 결과물을 다운로드할 수 있습니다.

참조사항
Detections/Dataset: COCO
Evaluation: tc-nn-toolkit을 이용하여 측정한 결과입니다.
- Evaluation Result의 FP32: .enlight 확장자로 변환된 상태에서 측정된 값입니다.
Inference Time: N-Dolphin EVB에서 실행한 결과입니다.
Reference: 신경망 모델의 원본 GitHub 링크로 연결됩니다.
-->

![YOLO Model Performance](../../docs/image/yolo_performance.png)

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
            <th colspan="2">AP@[.50:.95]</th>
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
            <td align="center"><a href="MobileNet/lite-model_ssd_mobilenet_v1_100_320_fp32_nms_1/">mb1-ssd-lite</a></td> <!-- Model -->
            <td align="center">TensorFlow Lite</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">320x320x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">8</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">44</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">2.54</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.219</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.212</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://tfhub.dev/iree/lite-model/ssd_mobilenet_v1_100_320/fp32/nms/1">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="MobileNet/mb2_ssd_lite/">mb2-ssd-lite</a></td> <!-- Model -->
            <td align="center">ONNX</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">300x300x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">4</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">56</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">2.08</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.006</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.006</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://github.com/openedges/pytorch-ssd">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov3/">yolov3</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">60</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">232</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">66.3</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.439</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.386</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://github.com/ultralytics/yolov3">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov4/">yolov4</a></td> <!-- Model -->
            <td align="center">Darknet</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">608x608x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">62</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">308</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">60.14</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.501</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.402</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://github.com/AlexeyAB/darknet/blob/master/cfg/yolov4.cfg">.cfg<a> <a href="https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights">.weights<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov5/yolov5n/">yolov5n</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">2</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">80</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">9.38</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.246</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.213</td> <!-- Evaluation Result: INT8 -->
            <td align="center" rowspan="5"><a href="https://github.com/ultralytics/yolov5">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov5/yolov5s/">yolov5s</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">7</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">144</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">14.7</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.342</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.303</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov5/yolov5m/">yolov5m</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">21</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">188</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">34.9</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.424</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.385</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov5/yolov5l/">yolov5l</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">45</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">308</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">55.17</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.461</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.406</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov5/yolov5x/">yolov5x</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">83</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">460</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">107.53</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.478</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.437</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov6/yolov6n/">yolov6n</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">5</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">40</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">6.75</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.353</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.332</td> <!-- Evaluation Result: INT8 -->
            <td align="center" rowspan="4"><a href="https://github.com/meituan/YOLOv6">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov6/yolov6s/">yolov6s</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">18</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">84</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">20.96</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.422</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.384</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov6/yolov6m/">yolov6m</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">34</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">116</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">37.96</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.468</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.462</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov6/yolov6l/">yolov6l</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">57</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">240</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">69.06</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.496</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.489</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov7/">yolov7</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">36</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">244</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">55.0</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.479</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.421</td> <!-- Evaluation Result: INT8 -->
            <td align="center"><a href="https://github.com/WongKinYiu/yolov7">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov8/yolov8n/">yolov8n</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">4</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">72</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">8.63</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.344</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.364</td> <!-- Evaluation Result: INT8 -->
            <td align="center" rowspan="5"><a href="https://github.com/ultralytics/ultralytics">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov8/yolov8s/">yolov8s</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">11</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">92</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">16.17</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.459</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.442</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov8/yolov8m/">yolov8m</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">25</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">156</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">45.35</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.472</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.458</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov8/yolov8l/">yolov8l</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">42</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">248</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">69.16</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.544</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.529</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yolov8/yolov8x/">yolov8x</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">66</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">436</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">118.06</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.559</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.540</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yoloX/yolox_s/">yolox_s</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">9</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">188</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">26.29</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.355</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.350</td> <!-- Evaluation Result: INT8 -->
            <td align="center" rowspan="6"><a href="https://github.com/Megvii-BaseDetection/YOLOX">GitHub<a></td> <!-- References: Link -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yoloX/yolox_m/">yolox_m</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">25</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">236</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">52.79</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.424</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.371</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yoloX/yolox_l/">yolox_l</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">52</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">372</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">79.72</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.450</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.442</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yoloX/yolox_x/">yolox_x</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">95</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">560</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">141.12</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.432</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.418</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yoloX/yolox_tiny/">yolox_tiny</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">416x416x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">5</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">64</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">9.26</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.287</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.277</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center"><a href="Yolo/yoloX/yolox_nano/">yolox_nano</a></td> <!-- Model -->
            <td align="center">Pytorch</td> <!-- Framework -->
            <td align="center">COCO</td> <!-- Detections/DataSet -->
            <td align="center">416x416x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">INT8</td> <!-- Quantization Bit -->
            <td align="center">1</td> <!-- Compiled NN Information: Weight, Bias Binary Size(MB) -->
            <td align="center">64</td> <!-- Compiled NN Information: Command Binary Size(KB) -->
            <td align="center">6.71</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.209</td> <!-- Evaluation Result: FP32 -->
            <td align="center">0.069</td> <!-- Evaluation Result: INT8 -->
        </tr>
    </tbody>
</table>

