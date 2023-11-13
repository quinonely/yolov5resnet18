# YOLOv5 with ResNet18 
Yolov5 Integration with ResNet-18 architecture, built on MaxPool layer and Basic Blocks<br>
Architecture used for modern banknote feature detection to compare with MobileNetv2 integrated YOLOv5

```
                 from  n    params  module                                  arguments                     
  0                -1  1      9536  models.common.Conv                      [3, 64, 7, 2, 3]              
  1                -1  1         0  torch.nn.modules.pooling.MaxPool2d      [3, 2, 1]                     
  2                -1  1     73984  models.common.BasicBlock                [64, 64]                      
  3                -1  2    147968  models.common.BasicBlock                [64, 64]                      
  4                -1  1     73984  models.common.Conv                      [64, 128, 3, 2, 1]            
  5                -1  2    590848  models.common.BasicBlock                [128, 128]                    
  6                -1  1    295424  models.common.Conv                      [128, 256, 3, 2, 1]           
  7                -1  2   2361344  models.common.BasicBlock                [256, 256]                    
  8                -1  1   1180672  models.common.Conv                      [256, 512, 3, 2, 1]           
  9                -1  2   9441280  models.common.BasicBlock                [512, 512]                    
 10                -1  1    263168  models.common.Conv                      [512, 512, 1, 1]              
 11                -1  1         0  torch.nn.modules.upsampling.Upsample    [None, 2, 'nearest']          
 12           [-1, 6]  1         0  models.common.Concat                    [1]                           
 13                -1  3   2626560  models.common.C3                        [768, 512, 3, False]          
 14                -1  1    131584  models.common.Conv                      [512, 256, 1, 1]              
 15                -1  1         0  torch.nn.modules.upsampling.Upsample    [None, 2, 'nearest']          
 16           [-1, 4]  1         0  models.common.Concat                    [1]                           
 17                -1  3    657920  models.common.C3                        [384, 256, 3, False]          
 18                -1  1    590336  models.common.Conv                      [256, 256, 3, 2]              
 19          [-1, 14]  1         0  models.common.Concat                    [1]                           
 20                -1  3   2495488  models.common.C3                        [512, 512, 3, False]          
 21                -1  1   2360320  models.common.Conv                      [512, 512, 3, 2]              
 22          [-1, 10]  1         0  models.common.Concat                    [1]                           
 23                -1  3   9971712  models.common.C3                        [1024, 1024, 3, False]        
 24      [17, 20, 23]  1     91545  models.yolo.Detect                      [12, [[0, 1, 2, 3, 4, 5], [0, 1, 2, 3, 4, 5], [0, 1, 2, 3, 4, 5]], [256, 512, 1024]]
YOLOv5s summary: 243 layers, 33363673 parameters, 33363673 gradients, 76.5 GFLOPs
```

Reference:
https://github.com/ultralytics/yolov5
