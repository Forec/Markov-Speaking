# Markov Speaking （马尔科夫链随机文本生成）
> This project is an package generating random sentences by markov chain. If you have any problems/ideas, please [email me](mailto:forec@bupt.edu.cn), or open your PR. I feel honored to learn from your help.

## Platform
The `markov_speaking.py` is written in `Python 2.7`, using `jieba`, `codecs`, `random` and `re`. You need to install `jieba` by `pip2 install jieba`.

## Usage
* The `markov_speaking.py` provides a class `Markov`, the `init` of `Markov` is `__init__(self, filepath = None, mode = 0, coding="utf8")`. `filepath` is the file you want to parse, and the sentences the class build will base on this file. `mode` is 0 if you want to parse English, and 1 if Chinese. `coding` assigns the codec, default is UTF-8.
* Let `p` be a instance of `Markov`, you can use `p.train(self, filepath = '', mode = 0, coding="utf8")` to regenerate the instance.
* After you have built `p` and trained, you can use `p.say(length)` to generate a random sentence. The length is the max length of sentence to generate, default is 10.

## Examples For Use
You can download the Chinese novel 《笑傲江湖》 from [here](http://7xktmz.com1.z0.glb.clouddn.com/swords.txt), or English novel 《The Standard Bearer》 from [here](http://7xktmz.com1.z0.glb.clouddn.com/The_Standard_Bearer.txt).
```python
>>> import markov_speaking
>>> p = markov_speaking.Markov('swords.txt', 1)
Building prefix dict from the default dictionary ...
Loading model from cache /home/forec/cache
Dumping model to file cache /home/forec/cache
Loading model cost 1.578 seconds.
Prefix dict has been built succesfully.
>>> p.say(5)
忽然想到一计说道师伯令狐师兄行侠仗义。
```

## Update-logs
* 2016-10-10: Add project and build repository.
* 2016-10-11: Fix problems in English part: Not split words by sentences.
* 2016-10-12: Fix train function.
* 2016-10-13: Remove useless chinese upper condition.

# License
All codes in this repository are licensed under the terms you may find in the file named "LICENSE" in this directory.

# 授权声明
我已授权[实验楼](https://www.shiyanlou.com/)使用此仓库中的代码并发表此项目教程，你可以在这里查看对应的[教程](https://www.shiyanlou.com/courses/678)。
