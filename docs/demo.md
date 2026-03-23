# Multimodal Alignment Demo

This demo illustrates the temporal alignment between video, audio, and text.

---

## 🎬 Example Clip

<div id="main-card" style="background:#fff;padding:20px;border-radius:12px;box-shadow:0 4px 12px rgba(0,0,0,0.1);">

<div style="display:flex; gap:20px; flex-wrap:wrap;">

<!-- 视频 -->
<div style="flex:1; min-width:300px;">
<b>Video</b><br>
<video id="videoPlayer" width="100%" controls>
  <source id="videoSrc" src="videos/ami00075_002_lips.mp4" type="video/mp4">
</video>
</div>

<!-- 音频 -->
<div style="flex:1; min-width:300px;">
<b>Audio</b><br>
<audio id="audioPlayer" controls>
  <source id="audioSrc" src="audios/ami00075_002.wav" type="audio/wav">
</audio>

<br><br>

<b>Speech Metadata</b>
<div id="metadata" style="background:#f0f2f5;padding:10px;border-radius:8px;line-height:1.6;">
Source: 开会啦<br>
Language: Amis<br>
Duration: 6.0s<br>
Speaker: male, Adult<br>
Scene: Interview
</div>

</div>

</div>

<br>

<!-- 文本 -->
<b>Transcription</b>

<div id="text-amis" style="background:#f9fafc;padding:15px;border-radius:10px;">
<b>Amis:</b><br>
o ninengnengan namo a kamok i matini i o 'a'iyalaeho:masaopo kita.
</div>

<br>

<div id="text-zh" style="background:#f9fafc;padding:15px;border-radius:10px;">
<b>Chinese:</b><br>
你现在收看的节目是'a'iyalaho:我们开会了
</div>

</div>

---

## 📚 More Examples

<div style="display:flex; gap:20px; flex-wrap:wrap;">

<!-- 示例1 -->
<div onclick="loadSample(
'videos/pwn00002_001.mp4',
'audios/pwn00002_001.wav',
'Aicu a patarevan mavan a uri maqepuqepu itjen a mazazepezep,a maljavaljavar ta namasan pazangal a pacugan,aya sakamaya a kai a namayatucu.',
'意思是我们要在一起商议，讨论很重要的事务，这样的意思。',
'Source: 开会啦<br>Language: Paiwan<br>Duration: 11.0s<br>Speaker: male<br>Scene: Interview'
)" 
style="cursor:pointer;background:#fff;padding:15px;border-radius:10px;box-shadow:0 2px 8px rgba(0,0,0,0.1); width:300px;">
<b>Sample pwn00002</b><br>
Language: Paiwan<br>
Scene: Interview
</div>

<!-- 示例2 -->
<div onclick="loadSample(
'videos/pyu00061_001.mp4',
'audios/pyu00061_001.wav',
'pukasa merukezang nata temaramaw kema.',
'传说我们的巫术非常的厉害。',
'Source: 母语巢<br>Language: Puyuma<br>Duration: 6.0s<br>Speaker: Female<br>Scene: Cultural'
)" 
style="cursor:pointer;background:#fff;padding:15px;border-radius:10px;box-shadow:0 2px 8px rgba(0,0,0,0.1); width:300px;">
<b>Sample pyu00061</b><br>
Language: Puyuma<br>
Scene: Cultural
</div>

<!-- 示例3 -->
<div onclick="loadSample(
'videos/xsy00013_003.mp4',
'audios/xsy00013_003.wav',
'ra:amen ray 111 tinal'oemaeh noka SaySiyat koSa'en pinkotaay.',
'（我们）知道 111年适逢赛夏族的paStaay，',
'Source: 开会啦<br>Language: Saisiyat<br>Duration: 6.0s<br>Speaker: Female<br>Scene: Interview'
)" 
style="cursor:pointer;background:#fff;padding:15px;border-radius:10px;box-shadow:0 2px 8px rgba(0,0,0,0.1); width:300px;">
<b>Sample xsy00013</b><br>
Language: Saisiyat<br>
Scene: Interview
</div>

</div>

---

<script>
function loadSample(video, audio, amisText, zhText, meta){

    // 更新视频
    document.getElementById("videoSrc").src = video;
    document.getElementById("videoPlayer").load();

    // 更新音频
    document.getElementById("audioSrc").src = audio;
    document.getElementById("audioPlayer").load();

    // 更新文本
    document.getElementById("text-amis").innerHTML = "<b>Text:</b><br>" + amisText;
    document.getElementById("text-zh").innerHTML = "<b>Chinese:</b><br>" + zhText;

    // 更新元信息
    document.getElementById("metadata").innerHTML = meta;

    // 自动滚动到上方展示区
    document.getElementById("main-card").scrollIntoView({behavior: "smooth"});
}
</script>