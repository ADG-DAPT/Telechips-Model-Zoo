
# **Telechips Model Zoo**
<a href="https://www.telechips.com/" target="_blank">
    <img src="./docs/image/telechips_ml_zoo_image.png" alt="Telechips ML Zoo">
</a>

Welcome to the Telechips Model Zoo!!

This repository provides a collection of neural network models optimized for Telechips AI SoCs (TCC750x). This repository includes a variety of models for tasks such as classification and object detection, is provided in a format ready to run on evaluation boards, and includes benchmark results that demonstrate the performance and efficiency of Telechips hardware.

<!--
텔레칩스 모델주(Model Zoo)에 오신 것을 환영합니다!

본 저장소는 텔레칩스 칩셋(TCC750X 등)에 최적화된 다양한 신경망 모델들을 제공합니다. Classification, Object Detection 등 여러 작업에 활용할 수 있는 신경망을 실제 보드에서 실행 가능한 형태로 제공하며, 칩 기반의 성능을 직접 확인할 수 있도록 성능 측정 결과도 함께 포함되어 있습니다.
-->

---

## **1. Chip Description**
Telechips offers three AI-enabled processors with integrated Neural Processing Units (NPU):

### TCC750x (N-Dolphin)
4+4 TOPS – Designed for high-performance ADAS and vision-based applications, supporting multi-camera processing, driver monitoring system (DMS), and advanced deep learning inference.

### TCC807x (Dolphin5)
TBD – Specifications will be announced soon.

### TCA200x (A2X): 
TBD – Specifications will be announced soon. 


These AI-enabled SoCs offer real-time neural network inference capabilities with high efficiency and scalability for automotive applications.

<!--
텔레칩스는 **NPU (Neural Processing Unit, 신경망 처리 장치)**가 내장된 세 가지 AI 프로세서를 제공합니다:

TCC750x: 8 TOPS – ADAS 및 비전 기반 애플리케이션을 위한 고성능 프로세서로, 멀티 카메라 처리, 운전자 모니터링(DMS), 고급 딥러닝 추론을 지원합니다.

TCC807x: 8 TOPS – 인포테인먼트 및 스마트 콕핏 시스템에 최적화되어 있으며, AI 기반 멀티미디어 처리, 음성 인식, 사용자 경험 향상 기능을 지원합니다.

TCA2x: TBD – 상세 사양은 추후 공개될 예정입니다.

이 칩셋들은 실시간 AI 추론을 가능하게 하며, 차량용 애플리케이션에서의 고효율성과 확장성을 제공합니다.
-->

---

## **2. Overview of Overall Model Zoo **
The following table summarizes the neural network models supported on Telechips hardware.
The name of each model links to its dedicated page with performance metrics and deployment instructions.
<!--
아래 표는 텔레칩스 칩에서 동작하는 신경망 모델 목록입니다.
각 모델명은 상세 페이지로 연결되며, 해당 칩에서의 성능 측정 결과를 확인하실 수 있습니다.
-->

### [TCC750x](./tcc750x/README.md)

<table border="1" cellspacing="0" cellpadding="5">
    <thead>
        <tr>
            <th rowspan="2" style="width:15%">Category</th>
            <th rowspan="2" colspan="2" style="width:25%">Model</th>
            <th rowspan="2" style="width:20%">Input Size (WxHxC)</th>
            <th rowspan="2" style="width:20%">Inference Time (ms)</th>
            <th rowspan="2" style="width:20%">Accuracy/
            mAP@50-95</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center" rowspan="1"><a href="tcc750x/Classification/README.md">Classification</a></td> <!-- Category -->
            <td align="center" colspan="2">MobileNetv2-10</td> <!-- Model -->
            <td align="center">224x224x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">1.31</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.6879</td> <!-- Accuracy -->
        </tr>
        <tr>
            <td align="center" rowspan="26"><a href="tcc750x/Object_detection/README.md">Object detection</a></td> <!-- Category -->
            <td align="center" colspan="2">Mb1_SSD_Lite</td> <!-- Model -->
            <td align="center">320x320x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">2.54</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.212</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" colspan="2">Mb2_SSD_Lite</td> <!-- Model -->
            <td align="center">300x300x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">2.08</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.006</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" colspan="2">YOLOv3</td> <!-- Model -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">66.3</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.386</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" colspan="2">YOLOv4</td> <!-- Model -->
            <td align="center">608x608x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">60.14</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.402</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" rowspan="5" class="model">YOLOv5</td> <!-- Models -->
            <td align="center" class="variant">n</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">9.38</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.213</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">14.7</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.303</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">34.9</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.385</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">55.17</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.406</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">x</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">107.53</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.437</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" rowspan="4" class="model">YOLOv6</td> <!-- Models -->
            <td align="center" class="variant">n</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">6.75</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.332</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">20.96</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.384</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">37.96</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.462</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">69.06</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.489</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" colspan="2">YOLOv7</td> <!-- Model -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">55.0</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.421</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" rowspan="5" class="model">YOLOv8</td> <!-- Models -->
            <td align="center" class="variant">n</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">8.63</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.364</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">16.17</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.442</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">45.35</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.458</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">69.16</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.529</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">x</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">118.06</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.540</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" rowspan="6" class="model">YOLOX</td> <!-- Models -->
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">608x608x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">26.29</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.350</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">52.79</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.371</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">79.72</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.442</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">x</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">141.12</td> <!-- Inference Time (ms/img) -->
            <td align="center">0.418</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">tiny</td> <!-- Models: Variant -->
            <td align="center">416x416x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">9.26</td> <!-- Inference Time (ms/img) -->
            <td align="center">0.277</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" class="variant">nano</td> <!-- Models: Variant -->
            <td align="center">416x416x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">6.71</td> <!-- Inference Time (ms/img) -->
            <td align="center">0.069</td> <!-- COCO AP@[.50:.95] -->
        </tr>
    </tbody>
</table>

---

## **3. History**
### Rev. 0.1.0: 2025-03-31
- Preliminary version release

---

## **4. To do**
- Telechips proprietary neural network upload scheduled (~June 30)
