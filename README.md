# Deepest_kaggle #

## 앙상블 준비하기 ## 
-----
### 업로드 위치 ###
1. 개인 결과물들은 deepest_kaggle/final_submission 안의 본인 폴더에 업로드해주세요.

### 업로드할 것(각자 정해진 폴더) ###
1. 훈련 코드
- 코드를 정리할 필요는 없음.

2. Validation set에 대한 valid_score.csv
- 15000여 개 validation set에 대한 score 점수를 업로드해야 합니다.
- 앙상블은 이 validation set에 대한 score로 하게 됩니다.
- validation set의 점수랑 test set에서의 점수가 차이가 나지만 우리는 믿음을 가지고 하기로 했습니다.

3. Test set에 대한 test_score.csv
- kaggle system에 제출한 점수를 파일명에 포함
- EX) test_score_0.9703.csv


### 유의 사항 ### 
1. 재현가능성
- 모델을 훈련할 때 deterministic하게 훈련될 수 있도록 random seed를 조절해주세요.(즉 모델의 성능이 reproducible하게 유의해주세요.)
- weight initialization 등은 tensorflow든 numpy든 random seed에 의존성이 있으므로 꼭 seed 설정을 해주세요.
- cudnn 자체가 non-deterministic한 특성이 있는데, 이 부분이 결과값에 크게 영향을 미치지는 않는다고 합니다. (특정 연산이 랜덤하게 수행되는 듯) 이 부분은 하면 좋고 굳이 안해도 그만, 

```python
seed = 940513  # (아무 정수)
# numpy
import numpy as np
np.random.seed(seed) 

# built-in random module
import random
random.seed(seed) 

# pytorch (gpu 포함)
import torch
torch.manual_seed(seed)
torch.cuda.manual_seed_all(seed)
torch.backends.cudnn.deterministic = True 

# tensorflow (gpu 포함되는지는 테스트안해봄.)
import tensorflow as tf
tf.set_random_seed(seed)

```


## Authors ## 
- [Jongho](https://github.com/sweetcocoa)
- [Jeeyung](https://github.com/jeeyung)
- [Junho](https://github.com/82magnolia)
- [Gawon](https://github.com/GawonNam)


