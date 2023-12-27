Google Chromeを使った動作確認
======================================


1. クライアントPCでGoogle Chromeブラウザを起動します。右上からシークレットモードで起動させます。

.. figure:: images/Picture1.jpg
   :scale: 50%
   :align: center


2. 右上からその他ツール - デベロッパーツールをクリックします。

.. figure:: images/Picture2.jpg
   :scale: 50%
   :align: center


3. Sources – Overrides - + Select folder for overridesをクリックします。

.. figure:: images/Picture3.jpg
   :scale: 50%
   :align: center


4. 任意のフォルダを作成し、フォルダーの選択をクリックします。

.. figure:: images/Picture4.jpg
   :scale: 50%
   :align: center


5. フォルダが作成されていることを確認します。

.. figure:: images/Picture5.jpg
   :scale: 50%
   :align: center


6. 対象URLにアクセスし、Networkタブをクリックします。対象の通信を選択し、右クリックで[Override content]を選択します。

.. figure:: images/Picture6.jpg
   :scale: 50%
   :align: center


7. Sources – Overridesに戻るとindex.htmlが表示されます。

.. figure:: images/Picture7.jpg
   :scale: 50%
   :align: center


8. CSD JSが最初に読み込まれるように、CSD JSと不審なドメインに対するJSスニペットを埋め込みます。

.. figure:: images/Picture8.jpg
   :scale: 50%
   :align: center


.. code-block:: cmdin
   ＜不審なドメインに対するJSスニペット サンプル＞
   <script>(function() { var s = document.createElement('script'); var domains = ["ganalitis.com", "ganalitics.com", "gstatcs.com", "webfaset.com", "fountm.online", "pixupjqes.tech", "jqwereid.online"]; for (var i = 0; i < domains.length; ++i) { s.src = 'https://' + domains[i]; } })();</script>


9. 最後に保存することで、*index.htmlからindex.htmlになります。

.. figure:: images/Picture9.jpg
   :scale: 50%
   :align: center


10. 対象サイトに数回アクセスを実施します。

.. figure:: images/Picture10.jpg
   :scale: 50%
   :align: center

