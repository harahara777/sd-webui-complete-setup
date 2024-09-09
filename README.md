# Stable Diffusion Webui Complete Setup  
Jupyter notebook for Stable Diffusion Web UI and Stable Diffusion Web UI Forge.

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
11. 3つのipynb拡張子のついたノートブックファイルがあります
   * `sd_webui_paperspace.ipynb` または `sd_webui_forge_paperspace.ipynb` はWebuiをインストールしたり起動するためのものです
   * `sd15_resource_lists.ipynb` ではSD 1.5のモデルや各種リソースをダウンロードできます
   * `sdxl_resource_lists.ipynb` ではSDXLのモデルや各種リソースをダウンロードできます
11.  [Paperspace Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Paperspace-Guide) や [Resource Lists Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Resource-Lists-Guide) に使い方の詳細が書いてあります

<br>

### Runpod  
1. [Sign up](https://runpod.io?ref=synjcfeg) and add some credit to your [balance](https://www.runpod.io/console/user/billing).
2. Open one of these template to create a Pod : [SD Web UI](https://runpod.io/console/gpu-cloud?template=38adx50leu&ref=synjcfeg) / [SD Web UI Forge](https://runpod.io/console/gpu-cloud?template=kwef1wl832&ref=synjcfeg)
3. Make sure the template is : 
   * SD Web UI : `ffxvs/sd-webui-containers:auto1111-latest`
   * SD Web UI Forge : `ffxvs/sd-webui-containers:forge-latest`
4. Select _Secure Cloud_ if you want to use _Network Volume (Persistent Storage)_, or Community Cloud if you want to use cheaper GPU.
5. Choose a GPU with at least 16GB VRAM, for example RTX A4000, RTX A4500, RTX 3090.
6. Continue and Deploy, then go to My Pods. Wait until the Pod is ready.
7. On the Pod you just created, click **Connect** then **Connect to HTTP Service [Port 8888]** to open Jupyterlab.
8. There will be 3 ipynb notebook files.
   * `sd_webui_runpod.ipynb` or `sd_webui_forge_runpod.ipynb` for installing Web UI.
   * `sd15_resource_lists.ipynb` for downloading SD v1.5 models.
   * `sdxl_resource_lists.ipynb` for downloading SDXL models.
9. Read [Runpod Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Runpod-Guide) and [Resource Lists Guide](https://github.com/ffxvs/sd-webui-complete-setup/wiki/Resource-Lists-Guide) to use the notebooks.
10. You can click **Connect to HTTP Service [Port 3001]** after installing and launching the Web UI.
11. Stop the Pod if you don't use it anymore. Terminate the pod to delete the Pod and its content. Don't forget to download images you generated.

<br>

### Download Notebooks manually
In case you can't download the latest notebooks from **Check for Updates** cell, you can download them manually from the links below :
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
