---
title: draft
tags:
---
<!-- 一些html和markdown用法 -->
<a id="demo">表格</a>

| 站点 | 地址  | 介绍 |
| ---- | :---: | ---: |
| f    |   w   |    q |

<span style="color:#519D9E; ">颜色</span><br>
<span style="font-size:0.7em;">0.7em 文字大小演示</span>

<a href="#demo"><p style="text-align:center">跳至上表格</p></a>

<p style="text-align:center;color:#8EC0E4;font-size:1.5em;font-weight:bold;">
综合演示<br>
优雅的</p>

1[^1]

[^1]:优雅的脚注

<!-- 网页内嵌网页 -->
<iframe src="https://cheektan.github.io/" width="100%" height="500" name="topFrame"  resize="no" scrolling="yes" frameborder="0" id="topFrame"></iframe>

<!-- 折叠方法 -->
<details>
```
<p><b>好友申请备注</b></p>
<p><b>好友申请备注</b></p>
<p><b>好友申请备注</b></p>
```
</details>

```
<details>
<p><b>好友申请备注</b></p>
<p><b>好友申请备注</b></p>
<p><b>好友申请备注</b></p>
</details>
```

<!-- 每日一句 -->
<p><a id="rainbow" href=''>🌈获取中...</a></p>
<script>
fetch('https://api.eatrice.top/')
  .then(response => response.json())
  .then(data => {
      var rainbow = document.getElementById('rainbow');
      rainbow.innerHTML = data.Content;
      rainbow.href = "https://rainbow.eatrice.top/?ID=" + data.ID;
  })
    .catch(console.error)
</script>

<!-- css保留空格 -->
<style scoped>/*scoped只在当前组件生效*/
p{
  white-space: pre-wrap;
}
</style>
<p>   12    3      5</p>

<!-- 多img排列 -->

hexo clean | hexo generate | hexo server | hexo deploy
hexo new <title> | hexo new draft <title> | hexo public <draft-title> |hexo server --draft
&emsp; | &ensp; | &nbsp;

git st | git add . | git commit -m "" | git push