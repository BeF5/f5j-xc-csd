Google Chromeを使った動作確認
======================================


1. クライアントPCでGoogle Chromeブラウザを起動します。右上から [ シークレットモード ] で起動させます。

.. figure:: images/Picture1.png
   :scale: 50%
   :align: center


2. 右上から [ その他のツール ] - [ デベロッパー ツール ] をクリックします。

.. figure:: images/Picture2.png
   :scale: 50%
   :align: center


3.  [ Sources ] – [ Overrides ] - [ + Select folder for overrides ] をクリックします。

.. figure:: images/Picture3.png
   :scale: 50%
   :align: center


4. 任意のフォルダを作成し、 [ フォルダーの選択 ] をクリックします。

.. figure:: images/Picture4.png
   :scale: 50%
   :align: center


5. 以下のようにフォルダが作成されていることを確認します。

.. figure:: images/Picture5.png
   :scale: 50%
   :align: center


6. 対象URLにアクセスし、 [ Network ] タブをクリックします。対象の通信を選択し、右クリックで [ Override content ] を選択します。

.. figure:: images/Picture6.png
   :scale: 50%
   :align: center


7.  [ Sources ] – [ Overrides ] に戻ると作成したフォルダ配下に対象サイトのトップページ、本書では [ index.html ] が表示されます。

.. figure:: images/Picture7.png
   :scale: 50%
   :align: center


8. CSD JSが最初に読み込まれるように、CSD JSと不審なドメインに対するJSスニペットを挿入します。

.. figure:: images/Picture8.png
   :scale: 50%
   :align: center


.. code-block:: cmdin

   ＜不審なドメインに対するJSスニペット サンプル＞
   <script>(function() { var s = document.createElement('script'); var domains = ["ganalitis.com", "ganalitics.com", "gstatcs.com", "webfaset.com", "fountm.online", "pixupjqes.tech", "jqwereid.online"]; for (var i = 0; i < domains.length; ++i) { s.src = 'https://' + domains[i]; } })();</script>


9. 最後に保存することで、 [ *index.html ] から [ index.html ] になります。

.. figure:: images/Picture9.png
   :scale: 50%
   :align: center


10. 対象サイトに数回アクセスを実施します。

.. figure:: images/Picture10.png
   :scale: 50%
   :align: center


次章でXC CSDで、検知できているかを確認します。

