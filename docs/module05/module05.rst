運用監視方法
======================================

監視時は検出スクリプト一覧から脅威内容を確認し、スクリプトが意図しないドメインへアクセスしていないか確認することと、意図しないForm Fieldの読み取りがないかを確認します。


● 検出スクリプト一覧

   [ Home ] - [ Client-Side Defense ] - [ Monitoring ] - [ Script List ] から保護対象にて検出したスクリプトの一覧を表示可能です。各スクリプトをクリックすることで詳細確認が可能です。

　Statusの状態の説明は下表のとおりです。


.. csv-table::

   "NA - No Action Needed", "該当スクリプトでは不審な点を未検出"
   "Resolved - No Action Needed", "該当スクリプトでいくつかの不審な動作を検出したが、ユーザがすでにアクションを実行済"
   "AN - Action Needed", "注意が必要なスクリプトで不審な動作を検出"


.. figure:: images/Picture1.png
   :scale: 50%
   :align: center


※ 検出したスクリプトがどのドメインへ通信を行っているか、どのForm Fieldの値を読み取ろうとしているかの振る舞いが確認可能です。


● 意図する通信、意図しない通信のハンドリング

   `前章[4. XC Consoleでの確認]の4項,5項 <https://f5j-xc-csd.readthedocs.io/ja/latest/module04/module04.html>`_ をご参照ください。


● Form Fieldの読み取りを抑止

   (1). [ Home ] - [ Client-Side Defense ] - [ Monitoring ] - [ Form Fields ] から特定のスクリプトによって読み取られる全フォームフィールドを確認することが可能です。

   .. figure:: images/Picture3-1.png
      :scale: 50%
      :align: center


   (2). 特定のForm Fieldに対して、そのFieldを読み取ろうとするScriptがあった際に、Risk Scoreを ”High Risk” としてマークし、機微データへのアクセスリスクを管理することが可能です。

      該当Fieldの [ Actions ] から [ Mark as Sensitive ] を選択し、適用することで、当該Fieldを機微データとして取り扱うことが可能です。

      .. figure:: images/Picture3-2.png
         :scale: 50%
         :align: center


   (3). Form Fieldを読み取るスクリプトに対するMitigation Actionとして、意図するForm Fieldの読み取りの場合は [ Allow Read ] へ、意図しないForm Fieldの読み取りの場合は [ Block Read ] へ追加することが可能です。

      [ Home ] - [ Client-Side Defense ] - [ Monitoring ] - [ Script List ] から [ Form Fields Read ] に数値が記録されているスクリプトを確認し、 [ Form Fields Read ] の数字を選択します。

      .. figure:: images/Picture3-3.png
         :scale: 50%
         :align: center


   (4). 該当Scriptが読み取っているForm Filedの一覧が表示され、それぞれのRisk Levelを確認可能です。

      前述の [Mark as Sensitive]にて該当Fieldを機微データとして登録しておくと、このFieldを読み取ろうとするScriptは ”High Risk” として記録されます。

      これらのScriptによる該当Fieldの読み取り可否を確認の上、Mitigation Actionとして [ Allow Read ] もしくは [ Block Read ] を設定可能です。

      .. figure:: images/Picture3-4.png
         :scale: 50%
         :align: center


● Alertの通知設定

   CSDで発生したアラート通知の設定として、 [ Alert Receivers ] ではどこに対しAlert Logを飛ばすかを設定し、 [ Alert Policies ] では何のAlert Logを飛ばすか（ここではCSD Alert Log）を設定し、最後にそれらの設定内容を [ Active Alert Policies ] として有効化することで、CSDアラート通知を設定可能です。

   (1). Alert Receiversの設定
      [ Home ] - [ Audit Logs & Alerts ] - [ Alerts Management ] - [ Alert Receivers ] にて、 [ Add Alert Receiver ] を選択します。

      .. figure:: images/Picture4-1.png
         :scale: 50%
         :align: center


      .. figure:: images/Picture4-2.png
         :scale: 50%
         :align: center


      Receiverは下記から選択することが可能です。(2023/12時点)
       ・Slack
       ・PagerDuty
       ・OpsGenie
       ・Email
       ・SMS
       ・Webhook

      設定入力後、[ Save and Exit ] をクリックします。 [ Alert Receiver ] の設定が追加されます。

      .. figure:: images/Picture4-3.png
         :scale: 50%
         :align: center


   (2). Alert Policiesの設定

      [ Home ] - [ Audit Logs & Alerts ] - [ Alerts Management ] - [ Alert Policies ] にて、[ Add Alert Policy ] を選択します。

      .. figure:: images/Picture4-4.png
         :scale: 50%
         :align: center

      Alert Policy設定では、先ほど設定したAlert Receiverの設定を紐づけ、Policy Rulesから [ Security-CSD ] を選択します。
 
      .. figure:: images/Picture4-5.png
         :scale: 50%
         :align: center

      以下の通り、[ Security Alerts ] と [ Groups ] を選択します。
      + Security Alerts : Matching Group
      + Groups : Security-CSD
    
      .. figure:: images/Picture4-6.png
         :scale: 50%
         :align: center


      [ Show Advanced Fields ] をクリックすることで、通知間隔を調整可能です。

      .. figure:: images/Picture4-7.png
         :scale: 50%
         :align: center


      設定入力後、[ Save and Exit ] をクリックすることで、[ Alert Policy ] の設定が追加されます。

      .. figure:: images/Picture4-8.png
         :scale: 50%
         :align: center


   (3). Active Alertの設定
      [ Home ] - [ Audit Logs & Alerts ] - [ Alerts Management ] - [ Active Alert Policies ] にて、[ Select Active Alert Policies ] をクリックします。

      .. figure:: images/Picture4-9.png
         :scale: 50%
         :align: center


      [ Add Item ] をクリックします。

      .. figure:: images/Picture4-10.png
         :scale: 50%
         :align: center


      先ほど作成したAlert Policyを選択し、[ Save and Exit ] をクリックします。

      .. figure:: images/Picture4-11.png
         :scale: 50%
         :align: center


      Active Alert Policyとして追加されます（Namespaceは ”system” として作成されます）

      .. figure:: images/Picture4-12.png
         :scale: 50%
         :align: center


      以上の設定により、CSDアラートが発生した際に、指定したReceiverに対してアラート通知を飛ばすことが可能です。


これで、XC CSDのセットアップガイドは終了となります。

