# dacon_SMILES

# Daily Report
---
* 2021-09-05 : SIM_ver2, aug_ver2 attention 구조(Dim :1024) 로 실험
   * Sim은 valid 점수가 0.17, new는 0.16 정도가 나온다
* 2021-09-06 : SIM_ver2, aug_ver2 SATRN  구조로 실험
   * Sim은 valid 점수가 0.163, new는 0.153 정도가 나온다. -> SATRN이 attention 1024보다는 잘나온는거 같고 한 에폭당 2분정도 시간이 더 걸림
   * SATRN * 1024 dim으로 실험 해보자
* 어떤분이 [morded](https://pypi.org/project/mordred/)라는 라이브러리로 1800개의 피쳐를 뽑아내는것을 공유해 주셔서 실험해볼 예정
   * tabnet..?
* 2021-09-08 : loss를 꼭 L1을 써야할까..? MSE loss를 써보자
   * MSE를 쓰고나니 단일 모델 기준 최고 점수가 나옴
   * MSE + L1 loss를 사용하니 점수가 더 오름
   * loss 변경이 GAP을 라벨로 썻을때 만 잘나오는 것 같다.
* 2021-09-11 : SIM + 기본 이미지로 학습시킨 모델을 기본 이미지만으로 inferece했을떄 성능이 가장 잘 나왔다.
* 2021-09-14 : GAP,S1,T1을 한번에 예측해서 mean을 해보자
* 2021-0917 : SMILES를 일반 문장 처럼 embedding을 진행해도 될까??
   * embedding을 빼고 돌려 봤더니 살짝 성능 하락이 있었다.(0.13->0.14)
* 2021-09-18 : 작은 데이터셋으로 실험 진행
* 2021-09-22 : CNN만써도 성능이 비슷하게 나오거나 더 잘나온다.
* 2021-09-23 : SMILES, FP를 CONV1D 를 써서 해보는 성능이 너무 안나오고 학습이 엄청 불안정 하게 된다.
* 2021-09-25 : 마지막 실험으로 CNN SWIN을 사용한다.
* 2021-09-27 : KFOLD를 넣고 돌렸는데 코드 문제인지 별 효과가 없었다.
* final : 최종 적으로 SMILES 식이 길고 분자 구조가 복잡한 분자들의 GAP(S1-T1)이 작은 거 같아 길이가 긴것들에 한에 0.9만큼의 weight를 줘 성능을 올렸다. (28/220)


---
### Wandb : https://wandb.ai/opijae/dacon_samsung?workspace=user-opijae
### Colab : https://colab.research.google.com/drive/1qHPYJRktKl1paK2l4B3KSKd-7WAKwDpo?usp=sharing
