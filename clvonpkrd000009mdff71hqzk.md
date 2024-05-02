---
title: "Readwise Reader Custom Summary: A Game Changer! (and how to set your prompt)"
datePublished: Thu May 02 2024 02:58:31 GMT+0000 (Coordinated Universal Time)
cuid: clvonpkrd000009mdff71hqzk
slug: readwise-summary
tags: ai, summary, readwise

---

With just one click, I can get the essence of any videos, newsletters, or articles in my native language. I'm using a customized ReadWise summary prompt. I will show you why and how to do that in this video.

%[https://youtu.be/Fs-fJX6JZek] 

### Inspired by:

[https://raymondhouch.com/lifehacker/digital-workflow/reader-ghostreader-prompts/](https://raymondhouch.com/lifehacker/digital-workflow/reader-ghostreader-prompts/)

[https://twitter.com/i/bookmarks/all?post\_id=1773019152049144212](https://twitter.com/i/bookmarks/all?post_id=1773019152049144212)

### My Prompt

```plaintext
重要提示：如果原文有作者名和来源信息，请在总结时，直接使用作者名和来源的信息进行概要，而不要使用“作者”代称。例如：“Tim Ferriss在播客“Tim Ferriss Show 203”中，分享了3个关于……”
关于中文的排版原则：请根据语义，分出相应的自然段。 

请根据以下步骤,请以简体中文对文档进行整理、重构、要点提炼:

第一步:整理与重构

仔细阅读全文,理解文章的主旨、脉络和议题  
将文章内容按主题进行归类,形成层次分明、逻辑清晰的结构  
对归类后的各部分内容进行语言润色,使行文更加通顺、简洁  
尽可能保留原文的所有关键信息、数据和细节,力求做到信息零损失  
在各部分内容前加入恰当的标题,便于读者快速索引与定位

第二步:要点提炼

在整理重构的基础上,提炼出3-5个核心要点  
每个要点由一个主要论点和2-3个支撑性论据组成  
论据应来自于原文,能够有力佐证论点,起到画龙点睛之效  
要点应全面涵盖文章的核心论题,彰显文章的主旨和价值  
要点表述应简明扼要,避免冗长累赘,突出重点、一语中的

第三步:提取资源

找出文章中提及的工具、人物、书籍、文章或是其他涉及的资源  

对每个资源给出200字内的简要阐释，点明其独到之处  
提供资源的链接


另外，在阅读此文章时，我对以下部分进行了高亮，认为这些是文章的重点，给你学习参考： 

{% for highlight in document.highlights %} - {{ highlight.content }} {% endfor %} 

{#- 下面的 if-else 逻辑检查文档的长度。如果文档较长，它将使用关键句子以避免超出 GPT 提示窗口的限制。我们强烈建议除非您知道自己在做什么，否则不要更改此设置。-#}

 {% if (document.content | count_tokens) > 2000 %}
 {{ document.content | central_sentences | join('\n\n') }} 
{% else %} 
{{ document.content }} 
{% endif %}

基本格式：

""" 
标题：{{ document.title }} 
作者：{{ document.author }} 
来源：{{ document.domain }} 

概要：
核心要点：
资源：
 """ 

输出格式要求:

正文部分,以"概要"为标题  
要点提炼部分,以"核心要点"为标题,各要点用"要点1""要点2"等加以标示  
资源部分，以“资源”为标题
各部分之间用markdown语法分割,确保层次清晰、美观大方

其他要求:

输出内容需包含以上三部分,并按照"输出格式要求"指定的顺序排列  

在正式输出之前,请对整个回答再通读一遍,检查是否有任何错别字、标点误用或者语病等,力求做到完美无瑕  
在输出内容之后,请给出对于文中提到的内容，你的下一步行动建议。简洁说明2-3个行动即可。
```