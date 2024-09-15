# Stable Diffusion Webui Complete Setup  
Stable DiffusionのWeb ui及びFolk版用のジュピターノートブック

![Notebook_preview](https://github.com/ffxvs/sd-webui-complete-setup/assets/156585597/52855d70-7c6b-42af-aa15-9ea67c99a5e5)

## Features  
* SD Web UIとSD Web UI Forge版を使用可能
* paperspaceとRunpodをサポート
* 5GB以下の小さなコンテナを使用
* Web UIをインストールし、SD v1.5とSDXLモデル両方をダウンロードできます
* 最新のノートブックへの更新
* モデルやLora、embadding、生成画像などは共有ストレージに保存されます
* 有用な拡張機能をリスト化
* いくつかの有用なアニメや一般用、リアル系のモデルをリスト化
* いくつかの有用なLoraやembedding、アップスケーラーやVAEなどはリスト化されています
* URLから拡張機能やLora、embedding、アップスケーラー、VAEなどを追加することも可能

## 使い方 
### Paperspace  
1. Paperspaceに[登録](https://console.paperspace.com/signup) し、ProかGrowthのうちどれか一つのプランを [購読](https://www.paperspace.com/gradient/pricing) します
2. Create a projectからプロジェクトを作成し、create a notebookへ進みます
3. Launch a notebookへ進んだら、下の **"Start from Scratch"** へ進みます
4. ビデオメモリが16GB以上あるGPUを、サブスクプランと同一でFreeとついている中から選択します(Free-P5000以外)
5. Auto-shutdown timeoutを **6 hours** に変更
6. 下にある **View Advanced Options.** をクリック
7. Container直下のname欄に、以下のコマンドをコピー&ペーストなどで入力し、他の欄は空欄のままにします
   * Container's name
     * SD Web UI
       ```
       ffxvs/sd-webui-containers:auto1111-latest
       ```
     * SD Web UI Forge
       ```
       ffxvs/sd-webui-containers:forge-latest
       ```
   * Container's command
     ```
     bash /paperspace-start.sh
     ```
9.  Start notebookを押してrunningという表示が出るまで待ちます、これには1分から5分程度の時間がかかる場合があります
10. コンソール画面や各種データを見る場合はタブを複製しておきます、 左のバーにある **"Open in Jupyterlab"** ボタン (オレンジの丸いアイコン)を押します
11.  以下の3つのノートブックファイルがあるはずです
   * `sd_webui_paperspace.ipynb` または `sd_webui_forge_paperspace.ipynb` はWebuiをインストールしたり起動するためのものです
   * `sd15_resource_lists.ipynb` ではSD 1.5のモデルや各種リソースをダウンロードできます
   * `sdxl_resource_lists.ipynb` ではSDXLのモデルや各種リソースをダウンロードできます
11.  [Paperspace Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Paperspace-Guide) や [Resource Lists Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Resource-Lists-Guide) に使い方の詳細が書いてあります

<br>

### Runpod  
1. Paperspaceに[登録](https://runpod.io?ref=synjcfeg) し、クレジットを [残高](https://www.runpod.io/console/user/billing) に追加します
2. テンプレートの中からいずれかを開いてポッドを作成します : [SD Web UI](https://runpod.io/console/gpu-cloud?template=38adx50leu&ref=synjcfeg) / [SD Web UI Forge](https://runpod.io/console/gpu-cloud?template=kwef1wl832&ref=synjcfeg)
3. テンプレートが以下のようになっていることを確認してください : 
   * SD Web UI : `ffxvs/sd-webui-containers:auto1111-latest`
   * SD Web UI Forge : `ffxvs/sd-webui-containers:forge-latest`
4. _Network Volume (永続ストレージ)_ を使いたい場合は _Secure Cloud_ を選択します, より安価なGPUを使う場合は Community Cloud を選択します
5. 少なくとも 16GB VRAM 以上のGPUを選択肢します、例:RTX A4000, RTX A4500, RTX 3090
7. Continue を押し Deploy へと進みます, その後 My Pods へ行き、準備が完了するまで待ちます
8. 作成されたポッドの **Connect** をクリックし、**Connect to HTTP Service [Port 8888]** でジュピターラボを起動します
9. 以下の3つのノートブックファイルがあるはずです
   * `sd_webui_runpod.ipynb` または `sd_webui_forge_runpod.ipynb` はWebuiをインストールしたり起動するためのものです
   * `sd15_resource_lists.ipynb` ではSD 1.5のモデルや各種リソースをダウンロードできます
   * `sdxl_resource_lists.ipynb` ではSDXLのモデルや各種リソースをダウンロードできます
10. [Runpod Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Runpod-Guide) や [Resource Lists Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Resource-Lists-Guide) に使い方の詳細が書いてあります
11. Web UI をインストールして起動した後、**Connect to HTTP Service [Port 3001]** をクリックできます。
13. ポッドを使用をやめる場合は停止してください、ポッドを終了するとポッドとそのコンテンツは削除されます、事前に生成した画像等をダウンロードすることを忘れないでください

<br>

### ノートブックを手動でダウンロード
 **Check for Updates** から最新のノートブックをダウンロードできない場合、以下のリンクから手動でダウンロードできます
- SD Web UI for Paperspace : [sd_webui_paperspace.ipynb](https://ffxvs.github.io/sd-webui-complete-setup/sd-webui/sd_webui_paperspace.ipynb)
- SD Web UI for RunPod : [sd_webui_runpod.ipynb](https://ffxvs.github.io/sd-webui-complete-setup/sd-webui/sd_webui_runpod.ipynb) 
- SD Web UI Forge for Paperspace : [sd_webui_forge_paperspace.ipynb](https://ffxvs.github.io/sd-webui-complete-setup/sd-webui-forge/sd_webui_forge_paperspace.ipynb)
- SD Web UI Forge for RunPod : [sd_webui_forge_runpod.ipynb](https://ffxvs.github.io/sd-webui-complete-setup/sd-webui-forge/sd_webui_forge_runpod.ipynb)
- SD v1.5 resource lists : [sd15_resource_lists.ipynb](https://ffxvs.github.io/sd-webui-complete-setup/resource-lists/sd15_resource_lists.ipynb)
- SDXL resource lists : [sdxl_resource_lists.ipynb](https://ffxvs.github.io/sd-webui-complete-setup/resource-lists/sdxl_resource_lists.ipynb)

<br>

## Credits
* [fast-stable-diffusion](https://github.com/TheLastBen/fast-stable-diffusion) by TheLastBen
* [stable-diffusion-webui-colab](https://github.com/camenduru/stable-diffusion-webui-colab) by Camenduru
* [stablediffusion_webui](https://github.com/sagiodev/stablediffusion_webui) by sagiodev
