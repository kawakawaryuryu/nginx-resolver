# nginx-resolver
resolverパラメータ確認用

## 背景
Nginxのデフォルト挙動はstart or relaod時にIPを保持してしまうため、proxy_pass等で設定されたドメインはずっと同じIPを向いてしまう。  
そのためresolverを設定することで回避する

## 確認方法
access.logに$upstream_addrを付けたことでストリーム先のIPをはけるようになったのでそれで接続先を確認

## 確認環境
### Docker
```bash
cd docker

# ビルド&起動
docker-compose up -d --build
```

### Vagrant
```bash
cd vagrant

# 起動
vagrant up

# nginx.confをVMにコピー
scp nginx.conf <VMのIP>:/etc/nginx/

# ssh
vagrant ssh
```

## 参考
[Qiita](https://qiita.com/kawakawaryuryu/items/af5dcb59aea1a10e4939)を書くのに確認した
