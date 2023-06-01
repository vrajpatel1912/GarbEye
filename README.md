## GarbEye - Garbage Automation Solution
![Garbeye](https://github.com/DynamVraj/GarbEye/assets/99869914/9a65d8bc-f3ae-4414-bc57-0676b6c05b3f)


Here, We are targeting complete automation of the garbage collection system which includes identification of garbage. This is the critical task where knowledge of image processing and machine learning will be applied. 
### Steps:
1. Create Virtual Environment.(Optional)

   python -m venv yolov7_custom
   
   source yolov7_custom/bin/activate

2. Annonate dataset using labelImg in YOLO format.

   To install labelImg use command "pip install labelImg" in your command prompt and after installation type "labelImg" in command prompt and annonate your data.
  
  ![image](https://github.com/DynamVraj/GarbEye/assets/99869914/58fd83a0-3148-4550-8579-26a9c2c78e66)

3. Split the dataset in train and val folder and save images and labels in data folder as shown below.

   ![image](https://github.com/DynamVraj/GarbEye/assets/99869914/2f6ad356-289f-4cf6-8a66-b39070d29298)

4. Install pre-reuirements for YOLOv7 by running "pip install -r requirements.txt" and "pip install -r requirements_gpu.txt".

5. Modify "data/custom_data.yaml" and "cfg/training/yolov7-custom.yaml" files.

6. Install YOLOv7 model using this link : "https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt".

7. Train YOLOv7 on custom dataset.
   
   code : "python train.py --workers 1  --device 0 --batch-size 8 --epochs 100 --img 640 640 --data data/custom_data.yaml --hyp data/hyp.scratch.custom.yaml --cfg cfg/training/yolov7-custom.yaml --name yolov7_custom --weights yolov7.pt"
   
   After running the above code it will create runs folder and store te training information in runs/train/yolov7-custom.
   
8. Testing on images
   
   code : "python detect.py --weights runs/train/yolov7-custom/weights/best.pt --img-size 640 --source image_test.jpg --view-img --no-trace"
   
Working Video:

https://github.com/DynamVraj/GarbEye/assets/99869914/9f1cf7b8-e3e8-4f77-ba42-963625da549f
