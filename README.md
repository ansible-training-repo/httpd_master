httpd Role
=========

httpdサービスの構築用Role

Requirements
------------

Roleに必要なパッケージはtox.ini、requirements.txtを参照すること。

Role Variables
--------------

次の変数はデフォルト変数で定義されている。
設定例はdefaults/main.ymlを参照。

以下の変数は設定必須 (デフォルト値なし)

- httpd_domain: ドメイン名を指定。ServerName、DocumentRootのディレクトリ名として利用(string)

以下の変数は必要に応じて設定

- httpd_port: バインドするポート番号を指定(number)
- httpd_packages: httpdサービスに必要なパッケージ名をlist形式で指定(string)


Dependencies
------------

なし

Example Playbook
----------------

設定必須のRole変数をインベントリ変数などで設定の上実行すること。
以下はPlaybook内で設定した場合の例。

```yaml
---
- name: Playbook
  hosts: webs
  gather_facts: false
  vars:
    httpd_port: 8008
    httpd_domain: hogehoge.com

  roles:
    - role: httpd

```
