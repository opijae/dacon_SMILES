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
