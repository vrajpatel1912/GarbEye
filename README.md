## GarbEye - Garbage Automation Solution
![Garbeye](https://github.com/DynamVraj/GarbEye/assets/99869914/5aeae7b2-da07-44b9-afc6-52fea02a8097)

Here, We are targeting complete automation of the garbage collection system which includes identification of garbage. This is the critical task where knowledge of image processing and machine learning will be applied. 
### Steps:
1. Create Virtual Environment.(Optional)

2. Annonate dataset using labelImg in YOLO format.

   To install labelImg use command "pip install labelImg" in your command prompt and after installation type "labelImg" in command prompt and annonate your data.
  
   ![image](https://github.com/DynamVraj/GarbEye/assets/99869914/335d5380-d055-41a3-a3b1-c27f171472b4)

3. Split the dataset in train and val folder and save images and labels in data folder as shown below.

   ![image](https://github.com/DynamVraj/GarbEye/assets/99869914/05be2f41-0ac8-43fc-8f4e-7f01dbf2e425)

4. Install pre-reuirements for YOLOv7 by running "pip install -r requirements.txt" and "pip install -r requirements_gpu.txt".

5. Modify "data/custom_data.yaml" and "cfg/training/yolov7-custom.yaml" files.

6. Install YOLOv7 model using this link : "https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt".

7. Train YOLOv7 on custom dataset.
   
   code : "python train.py --workers 1  --device 0 --batch-size 8 --epochs 100 --img 640 640 --data data/custom_data.yaml --hyp data/hyp.scratch.custom.yaml --cfg cfg/training/yolov7-custom.yaml --name yolov7_custom --weights yolov7.pt"
   After running the above code it will create runs folder and store te training information in runs/train/yolov7-custom.
   
8. Testing on images
   
   code : "python detect.py --weights runs/train/yolov7-custom/weights/best.pt --img-size 640 --source image_test.jpg --view-img --no-trace
   
Working Video:

https://github.com/DynamVraj/GarbEye/assets/99869914/3fcd5bad-d405-4863-a75a-cf1e3377d382

