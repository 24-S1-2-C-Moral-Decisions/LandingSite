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
Use all means to attract user clicks, write questionnaires

1. Use a story-based question
2. Save zone ->
   Superior to competitors: AI summary, visualization

The relationship between the two webs,

Responsive, mobile end, multilingual

server, survey data, code, Survey, AI Model

-->

## Other Notes & Information
meeting whiteboard https://anu365-my.sharepoint.com/:wb:/g/personal/u7619947_anu_edu_au/EXuva2xK4jdFh3alRcw_Ta0B3lFniwapAoO9Vf25Pce0VA?e=1IASW9

here are huggingface interfaces for 5 separate LLM models related to each MFD.
- https://huggingface.co/joshnguyen/mformer-authority
- https://huggingface.co/joshnguyen/mformer-care
- https://huggingface.co/joshnguyen/mformer-fairness
- https://huggingface.co/joshnguyen/mformer-loyalty
- https://huggingface.co/joshnguyen/mformer-sanctity

For predicting the probability of each MFD in the sentence/paragraph, you can use script here:
- https://huggingface.co/spaces/joshnguyen/mformer/blob/main/app.py
