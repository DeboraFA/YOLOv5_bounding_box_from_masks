# YOLO v5: Custom Dataset create bounding box from masks

1. Prepare dataset with bounding box
> run code Extract_bounding_box_from_masks

2. Download YOLO v5
! git clone  https://github.com/ultralytics/yolov5.git

3. Create file data.yaml in folder yolov5

train: REFEUGE/train # caminho dos dados de treino 

val: REFUGE/test # caminho dos dados de teste 

nc: 2 # quantidade de classe 

names: ['cup',  
        'disc']  


4. Train yolo (file train.py)
> python train.py --data data.yaml --weights yolov5s.pt --img 640 --batch-size 8 --name Model_refuge --epochs 60

resumo training
> python train.py --data data.yaml --weights best.pt

5. Exportar modelo onnx
> python export.py --weights runs/train/Model_refuge/weights/best.pt --include onnx --simplify --opset 12
