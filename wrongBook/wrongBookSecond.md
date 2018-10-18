### 1、Error: Can't set headers after they are sent



``` js
router.get('/test', async (req, res) => {
    
    res.send(result);        
});
```

- 原因： res.send() 了两次
- 解释： 因为通过app.all 验证接口，在执行 app.all() 的时候，误把验证成功给 res.send() 导致在 res.send(result); 执行的时候报错。