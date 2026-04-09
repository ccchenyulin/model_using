# [Minthy/ToriiGate-0.5](https://huggingface.co/Minthy/ToriiGate-0.5) 全格式中文说明与提示词速查手册

---

## 系统提示词（System Prompt）

在使用任何格式前，请在 Chatbox 的 **系统提示词** 设置中填入以下内容：

```
You are image captioning expert. Describe user's picture according to requested format and instructions.
```

## 格式速查总表

| 序号 | 格式名称 | 中文用途 | 需角色名 | 输出形式 | 推荐用途 | 📋 提示词模板（点击展开，顶部复制） |
|:---:|:---|:---|:---:|:---|:---|:---|
| 1 | Long Thoughts v2 | 最详细的结构化描述 | ✅ | 分章节长文本 | 制作高质量数据集 | <details><summary>🔽 点击展开 Long Thoughts v2 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Long Thoughts v2 模板<br>```<br><br>```text<br>Your answer must contain 6 parts:<br><format><br># 1. Thoughts about characters<br>You need to think here and compare peoples/creatures that you see on the picture with given popular tags, or descriptions, or your memories for each characters to determine who is who.<br># 2. Key details<br>Here you need to determine key details on comic and list them.<br># 3. Long description<br>Here come up with a long and detailed description of image content. Be creative, mention all detailes you listed above and other important things.<br># 4. Detailed description for each character<br>## Name 1<br>Detailed and long description for the first character<br>## Name 2<br>Same for each one (if present)<br></format><br>```</details> |
| 2 | Long Thoughts | 详细描述+个体部件列表 | ✅ | 分章节长文本 | 元素精细拆解 | <details><summary>🔽 点击展开 Long Thoughts 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Long Thoughts 模板<br>```<br><br>```text<br>Your answer must contain 6 parts:<br><format><br># 1. Thoughts about characters<br>You need to think here and compare peoples/creatures that you see on the picture  with given popular tags, or descriptions, or your memories for each characters to determine who is who.<br>If no characters are listed in input - just write here "No named characters"<br># 2. General description<br>A one-two paragraph summary of the image. Mention all individual parts/objects/characters/positions/interactions/etc.<br># 3. Detailed description for each character<br>## Character name 1 (put here the name if any)<br>In very detail write about features, poses, look, used objects, interactions, and other things for character on the picture.<br>## Character name 2 (put here the name if any)<br>Same for each character.<br>...<br># 4. Individual Parts<br>List the individual things you see in the image and their relative positions to other parts. Use a numbered list of between 5 and 20 items depending on image complexity.<br># 5. Texts on image<br>Mention every texts that you notice on image, including types (a speech bubble, watermark, banner, etc.) and content.<br># 6. Background and effects<br>Give some info about objects on background, describe the location (if seen). Then mention effects (style, camera angle, clarity/blurrines, effects like depth of field, strange angle/forshortening, etc.)<br></format><br>```</details> |
| 3 | Chroma-style | 模仿 Midjourney 风格 | ❌ | 四段式文本 | 直接作为 AI 绘图 Prompt | <details><summary>🔽 点击展开 Chroma-style 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Chroma-style 模板<br>```<br><br>```text<br>Your task is to describe the picture in very detail using a structure of 4 parts.<br>### 1. Regular Summary:<br>[A one-paragraph summary of the image. The paragraph should mention all individual parts/things/characters/etc.]<br>### 2. Individual Parts:<br>[List the individual things you see in the image and their relative positions to other parts. Use a numbered list of between 5 and 30 items depending on image complexity.]<br>### 3. Midjourney-Style Summary:<br>[A summary that has higher concept density by using comma-separated partial sentences instead of proper sentence structure.]<br>### 4. DeviantArt Commission Request<br>[Write a description as if you're commissioning this *exact* image via someone who is currently taking requests.]<br>```</details> |
| 4 | Minimalistic Structured Markdown | 简洁的 Markdown 结构 | ✅ | 带标题短文本 | 下游 Prompt 或展示 | <details><summary>🔽 点击展开 Minimalistic Markdown 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Minimalistic Structured Markdown 模板<br>```<br><br>```text<br>Your answer must contain 3 parts:<br><format><br># 1. Thoughts about characters<br>You need to think here and compare peoples/creatures that you see on the picture  with given popular tags, or descriptions, or your memories for each characters to determine who is who.<br>If no characters are listed in input - just write here "No named characters"<br># 2. Key details<br>Here you need to write about the key details on image, prefere using regular text.<br># 3. Structured description<br>## General<br>Write about general composition, content of image, background and all things that are not related to characters directly.<br>## Character name 1 (put here the name if any)<br>Write about datails and content related to specific character, including features, poses, look, used objects, interactions, and other things.<br>## Character name 2 (put here the name if any)<br>Same for each character.<br>## Image effects<br>Mention image effect, style, camera angle<br></format><br>In general stick to shorter descriptions.<br>```</details> |
| 5 | Minimalistic Structured Json | 机器最易读的 JSON | ❌ | JSON 字符串 | 批量数据处理 | <details><summary>🔽 点击展开 Minimalistic Json 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Minimalistic Structured Json 模板<br>```<br><br>```json<br>{"General" : "Here you need to come up with general/common information about picture, overall composition. Stick to shorter phrases and tags instead of long purple prose. Avoid bullets and markdown, write in plain text.",<br>"character_1 (put here the name if any)" : "Description of first character.",<br>"character_2 (if present" : "Description for second ",<br>"character_N": "...",<br>"image_effects" : "Mention here effects on image if there are any distinct.",<br>"texts" : "Speech bubbles, bars, marks, signs etc. with texts if present, else None",<br>"watermarks" : "If present"}<br>```</details> |
| 6 | Json | 功能更全的 JSON | ❌ | JSON 字符串 | 完整数据采集 | <details><summary>🔽 点击展开 Json 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Json 模板<br>```<br><br>```json<br>{"character" : "Description for character or object. Name (if defined), main details, features, position, pose, etc.",<br>"character_1" : "Description for first",<br>"character_2" : "Description for second ",<br>"character_N": "...",<br>"background" : "Detailed descritpion of background and it's content",<br>"image_effects" : "If there are some visual effects like fisheye distortion, chromatic aberration, glitches, messy drawing or anything else - write about it. If it's just a general anime art - omit this field.",<br>"texts" : "Speech bubbles, bars, marks, signs etc. with texts if present, else None",<br>"atmosphere" : "..."}<br>```</details> |
| 7 | Markdown Comic | 专门描述漫画分镜 | ✅ | 分章节 Markdown | 漫画分镜描述 | <details><summary>🔽 点击展开 Markdown Comic 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Markdown Comic 模板<br>```<br><br>```text<br>Use markdown format to describe to comic, 5 parts are recommended:<br><format><br># 1. Thoughts about characters<br>You need to think here and compare peoples/creatures that you see on the picture with given popular tags, or descriptions, or your memories for each characters to determine who is who.<br># 2. Key details<br>Here you need to determine key details on comic and list them.<br># 3. Comic format<br>In this section come up with the description of comic format, how many pages there are, horisontal/vertical orientation and other things. Optionally you can list main characters here.<br># 4. Details for each frame<br>## 4.1 Frame 1 (position)<br>Description for each frame, includding characters, objects, interactions, texts/speech bubbles and other things. Be detailed but not overdoo.<br>## 4.2 Frame 2 (position)<br>Same for each frame.<br>...<br># 5. Extra comment<br>Here you should write general desciption and some other info about the image.<br></format><br>```</details> |
| 8 | Json Comic | 机器可读的漫画描述 | ❌ | JSON 字符串 | 批量处理漫画数据集 | <details><summary>🔽 点击展开 Json Comic 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Json Comic 模板<br>```<br><br>```json<br>{<br>"comic_format": "menation the format, for example Comic of N frames",<br>"1st_frame": "Main description of the content for fist frame",<br>"2nd_frame": "Same for the second",<br>"Nth_ftame": "...",<br>"character_1": "Describe the characters in comic",<br>"character_N": "Separate description for each",<br>"meaning": "Try to guess general mood, vibe and meaning of the comic"<br>}<br>```</details> |
| 9 | Long / Short | 普通纯文本描述 | ❌ | 纯文本段落 | 快速获取纯文本描述 | <details><summary>🔽 点击展开 Long 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Long 模板<br>```<br><br>```text<br>Make a caption for given image with natural text. Use 2 to 5 paragraphs. Make your description long and vivid, mentioning all the details.<br>```</details><details><summary>🔽 点击展开 Short 模板</summary><br><br>**👇 点击下方代码块右上角的 📋 即可复制：**<br><br>```text<br>点击此处复制完整 Short 模板<br>```<br><br>```text<br>The caption for image should be quite short without long purple prose and slop. Cover main objects and details.<br>```</details> |

---


---

## 1. Long Thoughts v2

**中文说明**：最详细的结构化描述，包含角色推理、关键细节、长描述和分角色详细描述。适合制作高质量图像描述数据集。

**是否需要角色名**：✅ 是（若未提供角色名，需在提示词中要求模型自行识别）

**输出形式**：分章节的 Markdown 长文本

**推荐用途**：制作高质量数据集

**完整提示词模板（直接复制）**：

```
# Captioning format:
Your answer must contain 6 parts:
<format>
# 1. Thoughts about characters
You need to think here and compare peoples/creatures that you see on the picture with given popular tags, or descriptions, or your memories for each characters to determine who is who.
# 2. Key details
Here you need to determine key details on comic and list them.
# 3. Long description
Here come up with a long and detailed description of image content. Be creative, mention all detailes you listed above and other important things.
# 4. Detailed description for each character
## Name 1
Detailed and long description for the first character
## Name 2
Same for each one (if present)
</format>

# Characters on picture:
Try to recognize the characters in the picture and use their names.
```

---

## 2. Long Thoughts

**中文说明**：同样非常详细，但多了一个“个体部件列表”章节，用于逐一列举画面中的独立元素，适合精细拆解画面。

**是否需要角色名**：✅ 是

**输出形式**：分章节的 Markdown 长文本（共 6 部分）

**推荐用途**：元素精细拆解

**完整提示词模板（直接复制）**：

```
# Captioning format:
Your answer must contain 6 parts:
<format>
# 1. Thoughts about characters
You need to think here and compare peoples/creatures that you see on the picture with given popular tags, or descriptions, or your memories for each characters to determine who is who.
If no characters are listed in input - just write here "No named characters"
# 2. General description
A one-two paragraph summary of the image. Mention all individual parts/objects/characters/positions/interactions/etc.
# 3. Detailed description for each character
## Character name 1 (put here the name if any)
In very detail write about features, poses, look, used objects, interactions, and other things for character on the picture.
## Character name 2 (put here the name if any)
Same for each character.
...
# 4. Individual Parts
List the individual things you see in the image and their relative positions to other parts. Use a numbered list of between 5 and 20 items depending on image complexity.
# 5. Texts on image
Mention every texts that you notice on image, including types (a speech bubble, watermark, banner, etc.) and content.
# 6. Background and effects
Give some info about objects on background, describe the location (if seen). Then mention effects (style, camera angle, clarity/blurrines, effects like depth of field, strange angle/forshortening, etc.)
</format>

# Characters on picture:
Try to recognize the characters in the picture and use their names.
```

---

## 3. Chroma-style

**中文说明**：模仿 Midjourney 的提示词风格，输出包含“常规总结”、“个体部件列表”、“逗号分隔式总结”和“委托请求描述”四部分，非常适合直接用作 AI 绘图模型的 Prompt。

**是否需要角色名**：❌ 否

**输出形式**：四段式文本

**推荐用途**：直接作为 AI 绘图 Prompt

**完整提示词模板（直接复制）**：

```
# Captioning format:
Your task is to describe the picture in very detail using a structure of 4 parts.
### 1. Regular Summary:
[A one-paragraph summary of the image. The paragraph should mention all individual parts/things/characters/etc.]
### 2. Individual Parts:
[List the individual things you see in the image and their relative positions to other parts. Use a numbered list of between 5 and 30 items depending on image complexity.]
### 3. Midjourney-Style Summary:
[A summary that has higher concept density by using comma-separated partial sentences instead of proper sentence structure.]
### 4. DeviantArt Commission Request
[Write a description as if you're commissioning this *exact* image via someone who is currently taking requests.]

# Characters on picture:
Avoid to guess names for characters.
```

---

## 4. Minimalistic Structured Markdown

**中文说明**：简洁的 Markdown 结构化描述，包含角色推理、关键细节和分章节描述。篇幅较短，适合直接作为下游 Prompt 或展示。

**是否需要角色名**：✅ 是

**输出形式**：带标题的短 Markdown 文本

**推荐用途**：下游 Prompt 或展示

**完整提示词模板（直接复制）**：

```
# Captioning format:
Your answer must contain 3 parts:
<format>
# 1. Thoughts about characters
You need to think here and compare peoples/creatures that you see on the picture with given popular tags, or descriptions, or your memories for each characters to determine who is who.
If no characters are listed in input - just write here "No named characters"
# 2. Key details
Here you need to write about the key details on image, prefere using regular text.
# 3. Structured description
## General
Write about general composition, content of image, background and all things that are not related to characters directly.
## Character name 1 (put here the name if any)
Write about datails and content related to specific character, including features, poses, look, used objects, interactions, and other things.
## Character name 2 (put here the name if any)
Same for each character.
## Image effects
Mention image effect, style, camera angle
</format>
In general stick to shorter descriptions.

# Characters on picture:
Try to recognize the characters in the picture and use their names.
```

---

## 5. Minimalistic Structured Json

**中文说明**：机器最易读的 JSON 格式，字段简洁，适合批量处理、存入数据库或进一步编程分析。

**是否需要角色名**：❌ 否（但模型会尝试识别并填充字段名）

**输出形式**：JSON 字符串

**推荐用途**：批量数据处理

**完整提示词模板（直接复制）**：

```
# Captioning format:
Use json-style caption for given image with following structure:
{"General" : "Here you need to come up with general/common information about picture, overall composition. Stick to shorter phrases and tags instead of long purple prose. Avoid bullets and markdown, write in plain text.",
"character_1 (put here the name if any)" : "Description of first character."
"character_2 (if present" : "Description for second ",
"character_N"
...
"image_effects" : "Mention here effects on image if there are any distinct."
"texts" : "Speech bubbles, bars, marks, signs etc. with texts if present, else None",
"watermarks" : "If present",
}
Prefere shorter description and tags.

# Characters on picture:
Avoid to guess names for characters.
```

---

## 6. Json

**中文说明**：字段更丰富的 JSON 格式，包含氛围、文字、背景等完整字段，适合需要全面采集图像信息的场景。

**是否需要角色名**：❌ 否

**输出形式**：JSON 字符串

**推荐用途**：完整数据采集

**完整提示词模板（直接复制）**：

```
# Captioning format:
Use json-style caption for given image with following structure:
{"character" : "Description for character or object. Name (if defined), main details, features, position, pose, etc.",
/or in case of multiple
"character_1" : "Description for first"
"character_2" : "Description for second ",
"character_N"...
/or if there are no characters
"main content" : "long and detailed description of main content of image that might be the main focus if characters are missing",
/
"background" : "Detailed descritpion of background and it's content",
"image_effects" : "If there are some visual effects like fisheye distortion, chromatic aberration, glitches, messy drawing or anything else - write about it. If it's just a general anime art - omit this field."
"texts" : "Speech bubbles, bars, marks, signs etc. with texts if present, else None",
"atmosphere" : "...",
}
In special cases you can add extra keys.

# Characters on picture:
Avoid to guess names for characters.
```

---

## 7. Markdown Comic

**中文说明**：专为漫画/本子设计的描述格式，会按格子（frame）详细拆解每个分镜的内容，并包含角色推理和整体评论。

**是否需要角色名**：✅ 是

**输出形式**：分章节的 Markdown 文本

**推荐用途**：漫画分镜描述

**完整提示词模板（直接复制）**：

```
# Captioning format:
Use markdown format to describe to comic, 5 parts are recommended:
<format>
# 1. Thoughts about characters
You need to think here and compare peoples/creatures that you see on the picture with given popular tags, or descriptions, or your memories for each characters to determine who is who.
# 2. Key details
Here you need to determine key details on comic and list them.
# 3. Comic format
In this section come up with the description of comic format, how many pages there are, horisontal/vertical orientation and other things. Optionally you can list main characters here.
# 4. Details for each frame
## 4.1 Frame 1 (position)
Description for each frame, includding characters, objects, interactions, texts/speech bubbles and other things. Be detailed but not overdoo.
## 4.2 Frame 2 (position)
Same for each frame.
...
# 5. Extra comment
Here you should write general desciption and some other info about the image.
</format>

# Characters on picture:
Try to recognize the characters in the picture and use their names.
```

---

## 8. Json Comic

**中文说明**：机器可读的漫画描述 JSON 格式，输出包含漫画格式、每帧内容、角色描述和含义猜测，适合批量处理漫画数据集。

**是否需要角色名**：❌ 否

**输出形式**：JSON 字符串

**推荐用途**：批量处理漫画数据集

**完整提示词模板（直接复制）**：

```
# Captioning format:
Use json-style caption to describe to comin, stick to following structure:
{
"comic_format": "menation the format, for example Comic of N frames",
"1st_frame": "Main description of the content for fist frame",
"2nd_frame": "Same for the second",
...
"Nth_ftame": "...",
"character_1": "Describe the characters in comic",
...
"character_N": "Separate description for each",
"meaning": "Try to guess general mood, vibe and meaning of the comic"
}

# Characters on picture:
Avoid to guess names for characters.
```

---

## 9. Long / Short

**中文说明**：最基础的纯文本描述。Long 输出 2~5 段详细描述，Short 输出一句话左右简短描述。无需任何特殊结构，使用最简单。

**是否需要角色名**：❌ 否

**输出形式**：纯文本段落

**推荐用途**：快速获取纯文本描述

**Long 模板**：

```
# Captioning format:
Make a caption for given image with natural text. Use 2 to 5 paragraphs. Make your description long and vivid, mentioning all the details.

# Characters on picture:
Avoid to guess names for characters.
```

**Short 模板**：

```
# Captioning format:
The caption for image should be quite short without long purple prose and slop. Cover main objects and details.

# Characters on picture:
Avoid to guess names for characters.
```

---

## 使用建议

### 1. 在 Chatbox 中使用
将上述模板粘贴到输入框，然后上传图片即可。

### 2. 若已知角色名称（精确注入）
将模板中的 `Try to recognize the characters...` 替换为以下格式（推荐）：

```
# Characters on picture:
Here are names/tags for characters from the picture, make sure to use them: [角色A, 角色B].
```

### 3. 若已知 Booru 标签
在 `# Captioning format:` 之后添加一行：

```
# Booru tags for the image
[标签1 标签2 标签3]
```

### 4. 组合使用
可以同时提供角色名称和 Booru 标签，模型会优先使用这些信息进行识别和描述。

---

## 模型不适用场景

根据官方文档，ToriiGate-0.5 **不适用于**以下场景：

- 多轮对话和多图像输入
- OCR（光学字符识别）
- 纯文本输入和常规聊天
- 除图像描述外的任何通用 LLM 任务

该模型经过专门优化，仅擅长图像描述任务，其他功能已被精简。

---

## 注意事项

1. **角色名称格式**：使用 `Long Thoughts v2`、`Long Thoughts`、`Minimalistic Structured Markdown`、`Markdown Comic` 时，必须提供或让模型识别角色名称，否则输出质量下降。
2. **分辨率限制**：模型训练时平均分辨率约为 1 Mpx，建议输入图像不超过此分辨率（脚本会自动缩放）。
3. **输出可能不准确**：模型可能产生不准确或 provocative 的结果，请自行判断使用。
4. **不要修改提示词结构**：官方建议严格遵循上述提示词模板，大幅修改可能导致输出格式错乱。

---

## 版本历史

- 修正版 v2.0：补充推荐用途、角色名称精确注入格式、Booru 标签注入格式、模型不适用场景；修正 Minimalistic Structured Markdown 中 `In general stick to shorter descriptions.` 的位置。

---

*文档基于 ToriiGate-0.5 官方代码仓库（2025年12月）整理。*
