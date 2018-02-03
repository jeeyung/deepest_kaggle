## Augmentation 관련
> 텍스트는.. 보통 Augmentation을 안해요.

### 굳이 한다면..
- 단어 사이의 swap
- 어떤 단어를 지우고 그 window에서 발견되는 다른 임의의 word로 대체
- **그런 것보다는 보통 지우는 식으로 많이 함**
 - embedding 과정에서 dropout을 많이 거는 것과 비슷한듯?

## Model Structure
- 문장이 짧으니까 CNN >> RNN *(추측)*. 일단 embedded word vector(2차원이겠죠)에 대해 CNN을 해보세요.
- 혹시 잘 구분하지 못하는 것이 있으면 Tree Classification 도 고려.

## 그외 전처리
- word를 쪼개고 나면 보통 숫자같은 것들이 하나의 word로 나오는데 이걸 그냥 다 똑같은걸로 바꾸는 걸 추천
- label의 비율을 잘 맞춰야 하는데 이건 어려울 수도 있겠다.