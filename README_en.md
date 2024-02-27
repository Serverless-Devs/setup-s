# setup-s-aliyun
<p align="center">
  <span><b><a href="./README.md">中文</a> ｜ <a href="./README_en.md">English</a></b></span><br>
</p>

Setting up serverless-devs based on Aliyun Function Compute.

## Usage
You could add pre-steps before using setup-s, for example:

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

## Params
| Property |  Description   | Type |  Default  |
| ----- |  -------- | ---- | ---|
| provider |   required, service provider  |   string   | - |
| account_id |   account ID  |   string   | - |
| access_key_id  | optical account AK |  string    | - |
| access_key_secret  | optical account SK |   string   | - |
| secret_access_key  | optical account SK |   string   | - |
| secret_id  | optical account AK |   string   | - |
| secret_key  | optical account SK |   string   | - |
| access  | access alias |  string  | default |
| version | serverless-devs version |  3.0.0  | 3.0.0 |


More details about Aliyun Access Configs, please refer to [Serverless-devs doc](https://docs.serverless-devs.com/serverless-devs/default_provider_config#%E9%98%BF%E9%87%8C%E4%BA%91%E5%AF%86%E9%92%A5%E8%8E%B7%E5%8F%96)。


## Provider's Access Configs

| Provider | Required |
| --- | --- |
| alibaba |    AccountID, AccessKeyID, AccessKeySecret |
| aws |        AccessKeyID, SecretAccessKey|
| baidu |      AccessKeyID, SecretAccessKey|
| huawei |     AccessKeyID, SecretAccessKey|
| azure |      KeyVaultName, TenantID, ClientID, ClientSecret|
| tencent |    AccountID, SecretID, SecretKey|
| google |     PrivateKeyData |