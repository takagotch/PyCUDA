### pycuda
---
https://github.com/inducer/pycuda

https://mathema.tician.de/software/pycuda/

```py
// pycuda/sparse/operator.py

class OperatorBase(object):
  @property
  def dtype(self):
    raise NotImplementedError
    
  @property
  def shape(self):
    raise NotImplementedError
    
  def __neg__(self):
    return NegOperator(self)

class IdentityOperator(OperatorBase):
  def __init__(self, dtype, n):
    self.my_dtype = dtype
    self.n = n
    
  @property
  def dtype(self):
    return self.my_dtype
    
  @property
  def shape(self):
    return self.n, self.n
    
  def __call__(self, operand):
    return operand
    
class DiagonalPreconditioner(OperatorBase):
  def __init__(self, diagonal):
    self.diagonal = diagonal
    
  @property
  def dtype(self):
    return self.diagonal.dtype
    
  @property
  def shape(self):
    n = self.diagonal.shape[0]
    return n, n
    
  def __call__(self, operand):
    return self.diagonal*operand
```

```
```

```
```

