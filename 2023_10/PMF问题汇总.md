# PMF问题汇总

### 10.16

- lr = 0.0005 在 epoch8 左右 miou会出现下降
  - foc_loss + lov_loss + 原torch预训练模型
  - foc_loss + lov_loss + mindspore预训练模型
  - foc_loss + mindspore预训练模型
- pmf_ms 在华为云平台上出现未知报错
  - 删除lov_loss无报错
- lov_loss可能依旧存在一些问题？？？

### 10.17

- lr = 0.002
- 只保留backbone，测试torch和mindspore差异