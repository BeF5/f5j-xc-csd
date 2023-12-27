XC Client-Side Defense(CSD)とは
======================================

Client-Side Defense(以下、CSD)は、F5 Distributed Cloud Serviceの１つとして提供可能なWebスキミング対策用セキュリティSaaS型サービスです。

クライアントのブラウザ上で動作するjavascriptの動作をリアルタイムに監視し、F5が開発したシグナルに基づいて異常があった場合に管理者にアラートを上げ、データ流出のリスクを軽減することが可能となります。

CSDをご利用頂くことで、Webサイトにある「ユーザ名/パスワード」を入力するログイン画面や、クレジットカードの情報を入力するページなどに情報奪取のための不正なコードを仕込んだり、javascriptを改ざんして重要な情報を抜き取ったりする挙動を検知し、不正とみなした接続先についてブロックすることが可能となります。

- 動作概要構成図

.. figure:: images/Picture1.jpg
   :scale: 50%
   :align: center


.. figure:: images/Picture2.jpg
   :scale: 50%
   :align: center
