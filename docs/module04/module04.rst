XC Consoleでの確認
======================================


1. 対象アクセスから5分以上経過後に [ Home ] - [ Client-Side Defense ] - [ Dashboard ] で確認すると、不正なドメインへのアクセスを検知していることが確認できます。

.. figure:: images/Picture1.png
   :scale: 50%
   :align: center


2.  [ Dashboard ] では [ Auto-Refresh ] にて5分または15分でページの自動更新が可能です。

.. figure:: images/Picture2.png
   :scale: 50%
   :align: center


3.  [ Domain] をクリックすると、 Risk Score などが詳細情報が確認可能です。

   AI/MLによるRisk Score判定がHigh Riskに分類されると、 [ Status ] が [ Action Needed ] 表示となるため、意図するドメインへの通信の場合は [ Add To Allow List] へ、意図しないドメインへの通信の場合は [Add To Mitigate List] へ追加します。

.. figure:: images/Picture3.png
   :scale: 50%
   :align: center


4. 意図するドメインへの通信許可の設定

   (1). 対象DomainをAllow Listに追加します。

      対象Domainの一番右の [ Actions ] - [ ... ] から [ Add To Allow List ]をクリックします。

   .. figure:: images/Picture4-1.png
      :scale: 50%
      :align: center


   (2). 警告を確認し、 [ Add] を クリックでAllow Listへの登録は完了です。

   .. figure:: images/Picture4-2.png
      :scale: 50%
      :align: center


   (3). [ Monitoring ] – [ Network ] - [ Allow List ] から登録内容を確認可能です。

   .. figure:: images/Picture4-3.png
      :scale: 50%
      :align: center


5. 意図しないドメインへの通信遮断の設定

   (1). 対象DomainをMitigate Listに追加します。

      対象Domainの一番右の [ Actions ] - [ ... ] から [ Add To Mitigate List ]をクリックします。

   .. figure:: images/Picture5-1.png
      :scale: 50%
      :align: center


   (2). 警告を確認し、 [ Add ] をクリックでMitigate Listへの登録は完了です。

   .. figure:: images/Picture5-2.png
      :scale: 50%
      :align: center


   (3). [ Monitoring ] – [ Network ] - [ Mitigate List ] から登録内容を確認可能です。

   .. figure:: images/Picture5-3.png
      :scale: 50%
      :align: center

