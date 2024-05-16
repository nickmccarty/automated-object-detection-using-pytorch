# Automated Object Detection Using Pytorch:
## Storing Real-Time Detections for Downstream Analysis 

```mermaid
graph LR;
    GitHub_Actions[GitHub Actions Workflow] --> Cron[Cron Job Run Every 15 Minutes];
    Cron --> Python_Script[Python Script];
    Python_Script --> NYC_Traffic_Cam_Footage[Real-Time NYC Traffic Cam Footage];
    NYC_Traffic_Cam_Footage --> Object_Detection[Object Detection using PyTorch Vision];
    Object_Detection --> Detection_Output[Detection Output];
    Detection_Output -->Insert_DB[Insert into SQLite DB];
```

This workflow is quite linear and is effectively automated ETL in the sense that objects are being detected in NYC traffic cams every 15 minutes and the output is being stored in a database (`utc_timestamp`, `camera_location`, `detected_object`, `score`, and `bounding_box`); no other image data is retained or stored, as demonstrated in the Colab notebook provided below:

<a href="https://colab.research.google.com/drive/1fDSe36ragCs_POrMreZwHT-02ufjm9sF?usp=sharing#offline=true&sandboxMode=true" style="text-decoration: none;" target="_blank">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>
