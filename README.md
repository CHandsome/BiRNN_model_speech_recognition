# BiRNN_model_speech_recognition
用于学习记录BiRNN_model应用于语音识别
1.test_error:
  (1)维度不相同。训练模型与测试模型中，对于输入文本的处理不一致（例如：有无split()，replace()）
  (2)输出的向量没有0。没有考虑到空格的输入
  (3)label为空，有待查找
  (4)模型训练为空，文本标注与训练语音不标准，需要重新标注
2.实验条件以及结果
  (1) module:saver_01 dataset:train
      condition:
      batch_size = 2
      label = re.split('(\s)',label)
      epochs = 100
      if (batch + 1) % 2 == 0:
      
      result:
      Label err rate:  0.06923077
      file 0
      Original: Economy sets the tune whereas financial developments interact with economy
      Decoded:  Economy sets the tune financial developments interact with economy would would would would would would would would would                    would would would would would would would 
      file 1
      Original: The latest statistics from the National Bureau of Statistics shows that summer grain output of 2000 will decrease by 11                   million tons from that of 1999
      Decoded:  The latest statistics from the National Bureau of Statistics shows that summer output of 2000 will decrease by 11 million                 tons from that of 1999 
  (2) module:saver_02 dataset:data trn 增加到50条数据进行试验
       condition:
        batch_size = 2
        label = re.split('(\s)',label)
        epochs = 100
        if (batch + 1) % 2 == 0:
