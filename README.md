# setup-s
<p align="center">
  <span><b><a href="./README.md">中文</a> ｜ <a href="./README_en.md">English</a></b></span><br>
</p>

面向不同云厂商的 Serverless-devs 快速配置安装。

## 使用示例
可以按需在 setup-s 前添加前置 steps，例如

```yaml
steps:
  - uses: actions/checkout@v3    
  - uses: actions/setup-node@v4
    with:
      node-version: 14.14.0
```

### aliyun
```yaml
steps:
  - name: Setup Serverless-devs for aliyun
    uses: actions/setup-s@v1
    with:
      provider: aliyun
      version: 3.0.2
      account_id: ${{ secrets.ACCOUNT_ID }}
      access_key_id: ${{ secrets.ACCESS_KEYID }}
      access_key_secret: ${{ secrets.ACCESS_KEYSECRET }}
      access: aliyun_access
```

### aws
```yaml
steps:
  - name: Setup Serverless-devs for aws
    uses: actions/setup-s@v1
    with:
      provider: aws
      # version: 3.0.0
      access_key_id: ${{ secrets.ACCESS_KEYID }}
      secret_access_key: ${{ secrets.SECRET_ACCESSKEY }}
      access: aws_access
```

### huawei
```yaml
steps:
  - name: Setup Serverless-devs for huawei
    uses: actions/setup-s@v1
    with:
      provider: huawei
      # version: 3.0.2
      access_key_id: ${{ secrets.ACCESS_KEYID }}
      secret_access_key: ${{ secrets.SECRET_ACCESSKEY }}
      access: huawei_access
```

### tencent
```yaml
steps:
  - name: Setup Serverless-devs for tencent
    uses: actions/setup-s@v1
    with:
      provider: tencent
      account_id: ${{ secrets.ACCOUNT_ID }}
      secret_id: ${{ secrets.SECRET_ID }}
      secret_key: ${{ secrets.SECRET_KEY}}
      access: tencent_access
```

## 参数说明
| 字段 |  说明   | 类型 |  默认值  |
| ----- |  -------- | ---- | ---|
| provider |   必填，云厂商名称  |   string   | - |
| account_id |   部分厂商账号ID  |   string   | - |
| access_key_id  | 部分厂商账号AK |  string    | - |
| access_key_secret  | 部分厂商账号SK |   string   | - |
| secret_access_key  | 部分厂商账号SK |   string   | - |
| secret_id  | 部分厂商账号AK |   string   | - |
| secret_key  | 部分厂商账号SK |   string   | - |
| access  | 密钥别名 |  string  | default |
| version | 非必填，安装版本 |  3.0.0  | 3.0.0 |


密钥相关说明详见 [Serverless-devs 文档](https://docs.serverless-devs.com/serverless-devs/default_provider_config#%E9%98%BF%E9%87%8C%E4%BA%91%E5%AF%86%E9%92%A5%E8%8E%B7%E5%8F%96)。


## 常见云厂商密钥配置内容

| 云厂商 | 类型 |
| --- | --- |
| aliyun |    AccountID, AccessKeyID, AccessKeySecret |
| aws |        AccessKeyID, SecretAccessKey|
| huawei |     AccessKeyID, SecretAccessKey|
| tencent |    AccountID, SecretID, SecretKey|