# nginx-resolver
resolverパラメータ確認用

## 背景
Nginxのデフォルト挙動はstart or relaod時にIPを保持してしまうため、proxy_pass等で設定されたドメインはずっと同じIPを向いてしまう。  
そのためresolverを設定することで回避する

## 確認方法
access.logに$upstream_addrを付けたことでストリーム先のIPをはけるようになったのでそれで接続先を確認

## 修正
Qiita
