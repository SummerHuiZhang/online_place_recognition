# 2018年7月8日 取得图像特征后的匹配算法 波恩大学的olga Vysotska的工作
online_place_recognition: 
https://github.com/PRBonn/online_place_recognition
	
进一步完善的vpr-relocalization
https://github.com/PRBonn/vpr_relocalization
# 运行vpr-relocalization
在 cmake install
https://blog.csdn.net/qing666888/article/details/79090622
cmake ..没通过。。。懒得弄
就继续用online_place_recognition吧

# online_place_recognition:
Mac上编译通过了
论文中的性能测评是通过recall-percision -- **Fig 11**
本文有两个mode：
#### feature_description_based

**Step 1** ：每个图像都用OverFeat提取出来一个feature description保存为txt，
bin/linux_64/overfeat data/default/ -f pathto_image1.png pathto_image2.jpg
特征被print出来，如何存储下来呢？
需要改linux_64/overfeat对应的src/overfeat.cpp

存放形式如下：
query folder
    --image1_feature.txt
    --image2_feature.txt
    ...
    --imageN_feature.txt
reference folder
    --image1_feature.txt
    --image2_feature.txt
    ...
    --imageM_feature.txt
    
**Step 2**     
Fill the configuration file：详见https://github.com/SummerHuiZhang/Online_PlaceRecognition/tree/master/apps/feature_based_matching

**Step 3** 
./run_localizer_feature_based pathto/config.yaml

#### cosine matrix

# VPR
生成hash_features

```./hash_features ../../../examples/data/traj_2_Alderley/images/OverFeat_features/ overFeat traj_2_Alderley_hash```

