### GP-GNN

---

import git 报错
[解决方法:](https://stackoverflow.com/questions/48399498/git-executable-not-found-in-python)
再import git 前面加上
```python
os.environ["GIT_PYTHON_REFRESH"] = "quiet"
```

RuntimeError: Expected tensor for argument #1 'indices' to have scalar type Long; but got CUDAType instead (while checking arguments for embedding)

[解决方法：](https://stackoverflow.com/questions/56360644/pytorch-runtimeerror-expected-tensor-for-argument-1-indices-to-have-scalar-t)
I would suggest you to check the input type I had the same issue which solved by converting the input type from int32 to int64.(running on win10) ex:
```python
x = torch.tensor(train).to(torch.int64)
```


RuntimeError: Expected object of scalar type Long but got scalar type Int for argument #2 ‘target‘ in call to _thnn_nll_loss_forward.
[解决方法](https://blog.csdn.net/wu_xin1/article/details/107990521)
将第二个位置的输入强制转换成torch.long格式

C:/software/pycharm/projects/GP-GNN-master/train.py:183: UserWarning: volatile was removed and now has no effect. Use `with torch.no_grad():` instead.
  Variable(torch.from_numpy(entity_markers.astype(int)), volatile=True).cuda(),
```python
with torch.no_grad:
    xxx
    xxx
```