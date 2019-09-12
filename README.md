# BiRNN_model_speech_recognition
用于学习记录BiRNN_model应用于语音识别
1.test_error:
  (1)维度不相同。训练模型与测试模型中，对于输入文本的处理不一致（例如：有无split()，replace()）
  (2)输出为空。没有考虑到空格的输入
  (3)label为空，有待查找
