# Meeting Minutes
## Meeting Information
**Meeting Date/Time:** 03/06/2024, 10am  
**Meeting Purpose:** Sync Up 
**Meeting Location:** HN buidling room 2.41  
**Note Taker:**  Xinlong Wu

## Attendees
- Xinlong Wu
- Shiying Cai
- Zhongzheng Huang
- Xuan Liu
- Ceming Fu

## Agenda Items

Item | Description
---- | ----
Prototype | • show prototype 
resources | • Jira etc.
Question | • whether can we publish info from https://anu365-my.sharepoint.com/:u:/g/personal/u7359185_anu_edu_au/EZ1w6TBPj8xPlo0xejd6GP4BhW5VlYw6T8aH5CsvWmLiDQ?e=xTEZUE <br> • lack of datafile like `data/words by topic.json`

## Discussion Items
Item | Who | Notes |
---- | ---- | ---- |
Modification of prototypes | Client | To find a way to attract users to click on the questionnaire |
Introduction to the available LLM | Client | There are currently 5 available AI models and will figure out how to share them with the team after the meeting |
Modification of SoW | Client | Tech stack, interaction between AI and user |

<!--
用尽办法吸引用户点击，写问卷
1. 用一个事迹的问题
2. Save zone -> 
优势于竟品：AI summary，可视化


两个web的关联，

响应式，移动端，多语言

server，surver data， code，Survey, AI Molde
-->

## Other Notes & Information
here are huggingface interfaces for 5 separate LLM models related to each MFD.
- https://huggingface.co/joshnguyen/mformer-authority
- https://huggingface.co/joshnguyen/mformer-care
- https://huggingface.co/joshnguyen/mformer-fairness
- https://huggingface.co/joshnguyen/mformer-loyalty
- https://huggingface.co/joshnguyen/mformer-sanctity

For predicting the probability of each MFD in the sentence/paragraph, you can use script here:
- https://huggingface.co/spaces/joshnguyen/mformer/blob/main/app.py
