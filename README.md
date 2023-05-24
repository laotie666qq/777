# Python 3.10.7 (tags/v3.10.7:6cc6b13, Sep  5 2022, 14:08:36) [MSC v.1933 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import hashlib
>>> import time
>>>
>>> # 定义一个挖矿函数
>>> def mine_block(previous_block_hash, transactions, difficulty):
...     nonce = 0
...     while True:
...         # 构造区块头
...         block_data = str(nonce) + previous_block_hash + transactions
...         block_hash = hashlib.sha256(block_data.encode()).hexdigest()
...
>>>         # 验证区块头是否满足难度要求
>>>         if block_hash[:difficulty] == "0" * difficulty:
  File "<stdin>", line 1
    if block_hash[:difficulty] == "0" * difficulty:
IndentationError: unexpected indent
>>>             return block_hash
  File "<stdin>", line 1
    return block_hash
IndentationError: unexpected indent
>>>
>>>         nonce += 1
  File "<stdin>", line 1
    nonce += 1
IndentationError: unexpected indent
>>>
>>> # 设置初始值
>>> difficulty = 4  # 难度，即哈希前四位必须是0
>>> previous_block_hash = "0000000000000000000000000000000000000000000000000000000000000000"
>>> transactions = "A向B转账10个比特币"
>>>
>>> # 挖矿过程
>>> start_time = time.time()
>>> mined_block_hash = mine_block(previous_block_hash, transactions, difficulty)
