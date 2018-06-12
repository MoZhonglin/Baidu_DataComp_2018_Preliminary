百度-西交大·大数据竞赛2018——商家招牌的分类与检测初赛代码

### 使用方法

首先运行 utils 文件夹中的 rebuild_datasets.py 文件，然后运行 densenet.py 文件。


### 功能简介

rebuild_datasets.py 会重新组织数据集的文件层次，将同类别图片放置于以类别号命名的文件夹之中。
densenet.py 为主模型，当前代码会使用已经训练好的权重文件。如要重新训练，可去掉第 189 与 190 行注释。


### 文件结构
.  
├── data                       重新组织的数据集  
│   ├── train                  
│   └── validation             
├── datasets                   原始数据集  
│   ├── test                   
│   ├── test.txt               
│   ├── train                  
│   └── train.txt              
├── densenet.py                主模型  
├── result                     
│   └── result.csv             结果文件  
├── utils                      
│   └── rebuild_datasets.py    重建数据集文件层次工具  
└── weights                    训练好的权重文件  


### 补充说明

1. 使用early stop必须要将训练集的一部分划分出来作为验证集。为了充分使用训练集，将early stop的epoch次数记录下来，然后使用完整的训练集进行训练。

2. 训练集中13和63类存在误分类的现象，对此进行了手动调整。

3. 删除了两张噪声图片：908fa0ec08fa513df7d00c42366d55fbb2fbd930.jpg   a5c27d1ed21b0ef4c531461dd6c451da80cb3e9c.jpg
