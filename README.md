# Robust ADAS Synthetic Augmentation
<p>
  <img src="visuals/kitti_dirty_finetune_v3_visuals/test/001187_mud.png_imp_4_gt.png" width="400" />
  <img src="visuals/kitti_dirty_finetune_v3_visuals/test/001187_mud.png_imp_4_finetuned.png" width="400" />
  <br>
</p>
This project focuses on enhancing the reliability of Advanced Driver Assistance Systems (ADAS) by addressing the "visibility gap" in computer vision. While modern object detection models perform exceptionally well in clear weather, their precision often collapses when faced with environmental hazards like rain or mud contamination.
To solve this, we developed a Robust Synthetic Augmentation Pipeline. Instead of relying on rare and expensive real world data collection, we engineered a suite of filters that simulate physical driving challenges on clean, high quality ADAS camera feeds.

### Visual abstract
```mermaid
    graph LR
    %% Input Source
    Clean[Clean ADAS Image] --> MaskGen

    %% The Contamination Engine
    subgraph Engine [Synthetic Cont Pipeline]
        GeneratedTextures[<b>Generated Textures</b><br/>Syntheticly Generated Mud & Rain Textures]
        MaskGen[<b>Mask Generation</b><br/>Generate Realistic Contamination Mask]
        
        GeneratedTextures --> ImageBlending
        MaskGen --> ImageBlending
        
        ImageBlending[<b>Image Blending</b><br/>Apply Texture & Mask to Clean Image]
    end

    %% Training and Output
    ImageBlending --> Dataset[Dirty Dataset]
    Dataset --> YOLO[YOLO Model Finetuning]
    YOLO --> Results[Robust Object Prediction]

    %% Styling
    style YOLO stroke:#FFF176
    style Engine fill:#616161,stroke:#1565C0,stroke-width:2px
    style Results stroke:#4CAF50
    style Dataset stroke:#795548
```


### Dataset used

### Data augmentation and generation methods

### Input/Output Examples

### Models and pipelines used

### Training process and parameters

### Metrics

### Results

### Synthetic Contamination Results

### Repository structure

### Team Members
