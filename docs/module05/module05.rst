運用監視方法
======================================

監視時は検出スクリプト一覧から脅威内容を確認し、スクリプトが意図しないドメインへアクセスしていないか確認することと、意図しないForm Fieldの読み取りがないかを確認します。


1. 検出スクリプト一覧
   Home > Client-Side Defense > Monitoring > Script Listから保護対象にて検出したスクリプトの一覧を表示可能。各スクリプトをクリックすることで詳細確認が可能です。


.. csv-table::

   "NA - No Action Needed", "該当スクリプトでは不審な点を未検出"
   "Resolved - No Action Needed", "該当スクリプトでいくつかの不審な動作を検出したが、ユーザがすでにアクションを実行済"
   "AN - Action Needed", "注意が必要なスクリプトで不審な動作を検出"


.. figure:: images/Picture1.jpg
   :scale: 50%
   :align: center


※ 検出したスクリプトがどのドメインへ通信を行っているか、どのForm Fieldの値を読み取ろうとしているか、振る舞いが確認可能です。


.. figure:: images/Picture2.jpg
   :scale: 50%
   :align: center


2. 意図しない通信を抑止
   Home > Client-Side Defense > Dashboard から DomainをクリックするとRisk Scoreなどが確認可能です。
   AI/MLによるRisk Score判定がHigh Riskに分類されると、StatusがAction Needed表示となるため、意図するドメインへの通信の場合は [Add To Allow List] へ、意図しないドメインへの通信の場合は [Add To Mitigate List] へ追加します。


.. figure:: images/Picture3.jpg
   :scale: 50%
   :align: center


.. figure:: images/Picture4.jpg
   :scale: 50%
   :align: center


.. figure:: images/Picture5.jpg
   :scale: 50%
   :align: center
