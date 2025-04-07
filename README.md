
# **Telechips Model Zoo**
<a href="https://www.telechips.com/" target="_blank">
    <img src="./docs/image/telechips_ml_zoo_image.png" alt="Telechips ML Zoo">
</a> 

Welcome to the Telechips Model Zoo!!

This repository provides a collection of neural network models optimized for Telechips AI SoCs (TCC750x). This repository includes a variety of models for tasks such as classification and object detection, is provided in a format ready to run on evaluation boards, and includes benchmark results that demonstrate the performance and efficiency of Telechips hardware.

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


---

## **2. Overview of Overall Model Zoo**
The following table summarizes the neural network models supported on Telechips hardware.
The name of each model links to its dedicated page with performance metrics and deployment instructions.


### [TCC750x](./tcc750x/README.md)

<table border="1" cellspacing="0" cellpadding="5">
    <thead>
        <tr>
            <th rowspan="2" style="width:15%">Category</th>
            <th rowspan="2" colspan="2" style="width:25%">Model</th>
            <th rowspan="2" style="width:20%">Input Size (WxHxC)</th>
            <th rowspan="2" style="width:20%">Inference Time (ms)</th>
            <th rowspan="2" style="width:20%">Accuracy /
            mAP@50</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center" rowspan="1"><a href="tcc750x/Classification/README.md">Classification</a></td> <!-- Category -->
            <td align="center" colspan="2">mobileNetv2-10</td> <!-- Model -->
            <td align="center">224x224x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">1.24</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.687</td> <!-- Accuracy -->
        </tr>
        <tr>
            <td align="center" rowspan="26"><a href="tcc750x/Object_detection/README.md">Object detection</a></td> <!-- Category -->
            <td align="center" colspan="2">mb1_SSD_Lite</td> <!-- Model -->
            <td align="center">320x320x3</td> <!-- Input Size(WxHxC) -->
            <td align="center">2.46</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.367</td> <!-- COCO AP@[.50:.95] -->
        </tr>
        <tr>
            <td align="center" colspan="2">mb2_SSD_Lite</td> <!-- Model -->
            <td align="center">300x300x3</td> <!-- Input Size(WxHxC) -->
            <td align="center">2.00</td> <!-- Inference Time(msec): EVB -->
            <td align="center">0.651</td> <!-- Evaluation Result: INT8 -->
        </tr>
        <tr>
            <td align="center" colspan="2">YOLOv3</td> <!-- Model -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">63.60</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.598</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" colspan="2">YOLOv4</td> <!-- Model -->
            <td align="center">608x608x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">57.50</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.735</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" rowspan="5" class="model">YOLOv5</td> <!-- Models -->
            <td align="center" class="variant">n</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">8.97</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.383</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">13.74</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.509</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">32.96</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.584</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">54.01</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.619</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">x</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">104.11</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.643</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" rowspan="4" class="model">YOLOv6</td> <!-- Models -->
            <td align="center" class="variant">n</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">6.50</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.493</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">20.43</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.552</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">36.80</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.643</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">67.35</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.673</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" colspan="2">YOLOv7</td> <!-- Model -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">50.21</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.648</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" rowspan="5" class="model">YOLOv8</td> <!-- Models -->
            <td align="center" class="variant">n</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">8.09</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.488</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">15.49</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.576</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">39.31</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.632</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">67.04</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.654</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">x</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">113.31</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.664</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" rowspan="6" class="model">YOLOX</td> <!-- Models -->
            <td align="center" class="variant">s</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">24.52</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.467</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">m</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">49.35</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.536</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">l</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">77.11</td> <!-- Inference Time (msec): EVB -->
            <td align="center">0.565</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">x</td> <!-- Models: Variant -->
            <td align="center">640x640x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">136.51</td> <!-- Inference Time (ms/img) -->
            <td align="center">0.583</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">tiny</td> <!-- Models: Variant -->
            <td align="center">416x416x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">8.53</td> <!-- Inference Time (ms/img) -->
            <td align="center">0.401</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
        <tr>
            <td align="center" class="variant">nano</td> <!-- Models: Variant -->
            <td align="center">416x416x3</td> <!-- Input Size (WxHxC) -->
            <td align="center">6.09</td> <!-- Inference Time (ms/img) -->
            <td align="center">0.112</td> <!-- Evaluation Result: INT8 IoU=0.50 -->
        </tr>
    </tbody>
</table>

---

## **3. History**
### Rev. 0.1.0: 2025-04-07
- Preliminary version release

---

## **4. To do**
- Telechips proprietary neural network upload scheduled (by June 30)
