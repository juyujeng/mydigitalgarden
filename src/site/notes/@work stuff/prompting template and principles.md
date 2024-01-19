---
{"dg-publish":true,"permalink":"/@work stuff/prompting template and principles/","title":"prompting 模板與原則","tags":["ai","chatgpt","prompt"],"created":"2024-01-15T22:44","updated":"2024-01-18T00:23"}
---


[[Prompting\|Prompting]] 專指和[[Guidelines/Large language model\|大型語言模型]]互動（提問）的方式。好的prompting可用精簡、結構化的文字，提升[[Guidelines/Large language model\|大型語言模型]]回應內容的品質，更符合使用者的期待。

## prompting 模板

在撰寫prompts有模板可以粗略套用到各個情境，再按照使用者的實際情況酌以增減。這三個部份包含

1. **「提供明確的目標任務或問題」**
   - 需要[[Guidelines/Large language model\|大型語言模型]]協助完成的任務，或是想要獲得回應的問題
   - 這個部份是必要的
   - 例如： `什麼是信度？`
2. **「提供問答的情境」**
   1. **「[[Guidelines/Large language model\|大型語言模型]]要扮演的角色」**
      - 定義[[Guidelines/Large language model\|大型語言模型]]所扮演的角色，可以獲得基於不同的背景或角色特色的回應內容
      - 這一部份非是必要的，但若能正確地使用，能有效地提升回應內容的品質或是讓回應內容更接近使用者的期望。
      - 例如：`扮演一個教授研究方法的老師`
   2. **「受眾、回應風格與格式」**
      - 指定回應需符合的特定格式（如：表格、html）、限制（如：字數）或是文字風格（如：正式有禮貌）。
      - 這一部份按任務需要，可能是必要的
3. **「給予增強咒語」**
   - 這個部份為附加的句子或是關鍵詞，能夠提升回應內容的品質。但附加文字與目標任務在表面上不一定有相關。
   - 非必要
   - 例如：`let's go step by step`

## 26 prompting principles

Bsharat等人（2023）歸納出[[@work stuff/26 prompting principles\|26項prompting原則]]，並將這些原則分為5大類。結合前述的[[@work stuff/prompting template and principles#prompting 模板\|模板]]，我重新組織如下

1. 如何設定或說明任務、目標
   - 精簡、清楚地說明任務或是目標
     - 省略`請`、`我想要`等禮貌用詞
     - 以`你的任務是…`給指示
     - 給範例
   - 互動以釐清任務或目標
     - `若有不足的資訊，問我`
   - 簡化或拆解任務
     - 將複雜的問題拆解為多個子問題
2. 如何設定問答的情境
   - 定義大型語言模型要扮演的角色
   - 設定受眾、回應風格與格式
     - `假說我是11歲的小孩…`
3. 如何給予增強咒語
   - `答得好我會給你300元小費`
   - `如果不用簡單的語言說明我會處罰你`
   - `重複關鍵詞`
   - 使用output prime `……。說明：`
4. 如何結構化prompts
    - 標記區格prompts各部份
5. 特定任務模板

詳細的26項prompting原則如下：

## 如何設定或說明任務、目標

### 精簡、清楚說明任務或是目標

| Principle | Prompt Principle                                                                                                                                                                                              | Example Prompt                                                                                                                                                                                                                                                |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1         | If you prefer more concise answers, no need to be polite with LLM so there is no need to add phrases like “please", "if you don't mind", "thank you", "I would like to", etc., and get straight to the point. | Could you kindly describe the structure of a human cell, please?                                                                                                                                                                                              |
| 4         | Employ affirmative directives such as "do," while steering clear of negative language like "don't".                                                                                                           | How do buildings remain stable during earthquakes?                                                                                                                                                                                                            |
| 7         | Implement example-driven prompting (Use few-shot prompting).                                                                                                                                                  | Example 1: Translate the following English sentence to French: "The sky is blue." (Response: "Le ciel est bleu.") Example 2: Translate the following English sentence to Spanish: "I love books." (Response: "Amo los libros.")                               |
| 9         | Incorporate the following phrases: "Your task is" and "You MUST".                                                                                                                                             | Your task is to explain the water cycle to your friend. You MUST use simple language.                                                                                                                                                                         |
| 19        | Combine Chain-of-thought (Cot) with few-Shot prompts.                                                                                                                                                         | Example 1: "Divide 10 by 2. First, take 10 and divide it by 2. The result is 5."<br><br>Example 2: "Divide 20 by 4. First, take 20 and divide it by 4. The result is 5. "Main Question: "Divide 30 by 6. First, take 30 and divide it by 6. The result is...? |

### 互動以釐清任務或目標

| Principle | Prompt Principle                                                                                                                                                                                                                                                                                                 | Example Prompt                                                                                                                               |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| 14        | Allow the model to elicit precise details and requirements from you by asking you questions until it has enough information to provide the needed output (for example, "From now on, I would like you to ask me questions to...").                                                                               | From now on, please ask me questions until you have enough information to create a personalized fitness routine.                             |
| 15        | To inquire about a specific topic or idea or any information and you want to test your understanding, you can use the following phrase: "Teach me the [Any theorem / topic / rule name] and include a test at the end, but don't give me the answers and then tell me if I got the answer right when I respond". | Teach me the kvl law and include a test at the end, but don't give me the answers and then tell me if I got the answer right when I respond. |

### 簡化或拆解任務

| Principle | Prompt Principle                                                                            | Example Prompt                                                                                                                                                                                                                                              |
| --------- | ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 3         | Break down complex tasks into a sequence of simpler prompts in an interactive conversation. | Prompt: Distribute the negative sign to each term inside the parentheses of the following equation: 2x + 3y - (4x - 5y) Prompt: Combine like terms for 'x' and 'y' separately. <br><br>Prompt: Provide the simplified expression after combining the terms. |

## 如何設定問答的情境

### 如何定義[[Guidelines/Large language model\|大型語言模型]]要扮演的角色

| Principle | Prompt Principle                                   | Example Prompt                                                                                                                            |
| --------- | -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| 16        | Assign a role to the Large Language Models (LLMs). | If you were an expert economist, how would you answer: What are the key differences between a capitalist and a socialist economic system? |

### 如何設定回應格式或風格

| Principle | Prompt Principle                                                                                                                                                                                                                                                                                                                                                                                                                                    | Example Prompt                                                                                      |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| 2         | Integrate the intended audience in the prompt, e.g., the audience is an expert in the field.                                                                                                                                                                                                                                                                                                                                                        | Construct an overview of how smartphones work, intended for seniors who have never used one before. |
| 5         | When you need clarity or a deeper understanding of a topic, idea, or any piece of information, utilize the following prompts:<br>- Explain [insert specific topic] in simple terms.<br>- Explain to me like I'm 11 years old.<br>- Explain to me as if I'm a beginner in [field].<br>- Explain to me as if I'm an expert in [field].<br>- "Write the [essay/text/paragraph] using simple English like you're explaining something to a 5-year-old". | Explain to me like I'm 11 years old: how does encryption work?                                      |
| 11        | Use the phrase "Answer a question given in a natural, human-like manner" in your prompts.                                                                                                                                                                                                                                                                                                                                                           | Write a paragraph in natural language form about healthy food.                                      |

## 如何上BUFF

| Principle | Prompt Principle                                                                                                                                                                            | Example Prompt                                                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| 6         | Add "I'm going to tip $xxx for a better solution".                                                                                                                                          | I'm going to tip $300K for a better solution! Explain the concept of dynamic programming and provide an example use case.                             |
| 10        | Incorporate the following phrases: "You will be penalized".                                                                                                                                 | Your task is to explain the water cycle to your friend. You will be penalized if you don't use simple language.                                       |
| 12        | Use Leading words like writing "think step by step".                                                                                                                                        | Write a Python code to loop through 10 numbers and sum all of them. let's think step by step.                                                         |
| 13        | Add to your prompt the following phrase "Ensure that your answer is unbiased and does not rely on stereotypes".                                                                             | How do cultural backgrounds influence the perception of mental health? Ensure that your answer is unbiased and does not rely on stereotypes.          |
| 18        | Repeat a specific word or phrase multiple times within a prompt.                                                                                                                            | Evolution, as a concept, has shaped the development of species. What are the main drivers of evolution, and how has evolution affected modern humans? |
| 20        | Use output primers, which involve concluding your prompt with the beginning of the desired output. Utilize output primers by ending your prompt with the start of the anticipated response. | Describe the principle behind Newton's First Law of Motion. Explanation:                                                                              |

## 如何結構化prompts

將prompt組織為有結構化、易讀的形式

| Principle | Prompt Principle                                                                                                                                                                                                                                                         | Example Prompt                                                                                                           |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| 8         | When formatting your prompt, start with '###Instruction###', followed by either '###Example###' or '###Question###' if relevant. Subsequently, present your content. Use one or more line breaks to separate instructions, examples, questions, context, and input data. | ###Instruction### Translate a given word from English to French. ###Question### What is the French word for "book"?      |
| 17        | Use Delimiters.                                                                                                                                                                                                                                                          | Compose a persuasive essay discussing the importance of 'renewable energy sources' in reducing greenhouse gas emissions. |

## 特定任務模板

| Principle | Prompt Principle                                                                                                                                                                                                                                                                                                                        | Example Prompt                                                                                                                                                                                                                                                                                                           |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 21        | To write an [essay / text paragraph / article] or any type of text that should be detailed: "Write a detailed [essay / text / paragraph] for me on [topic] in detail by adding all the information necessary".                                                                                                                          | Write a detailed paragraph for me on the evolution of smartphones in detail by adding all the information necessary.                                                                                                                                                                                                     |
| 22        | To correct / change specific text without changing its style: "Try to revise every paragraph sent by users. You should only improve the user’s grammar and vocabulary and make sure it sounds natural. You should not change the writing style, such as making a formal paragraph casual".                                              | Try to revise every text sent by users. You should only improve the user's grammar and vocabulary and make sure it sounds natural. You should not change the writing style, such as making a formal paragraph casual. Paragraph: Renewable energy is really important for our planet's future. It comes from natural ... |
| 23        | When you have a complex coding prompt that may be in different files: "From now and on whenever you generate code that spans more than one file, generate a [programming language] script that can be run to automatically create the specified files or make changes to existing files to insert the generated code. [your question]." | Generate code that spans more than one file, and generate a Python script that can be run to automatically create the specified files for a Django project with two basic apps for different functionalities.                                                                                                            |
| 24        | When you want to initiate or continue a text using specific words, phrases, or sentences, utilize the following prompt:<br>- I'm providing you with the beginning [song lyrics / story / paragraph / essay...]: [Insert lyrics / words / sentence]. Finish it based on the words provided. Keep the flow consistent.                    | "The misty mountains held secrets no man knew." I'm providing you with the beginning of a fantasy tale. Finish it based on the words above.                                                                                                                                                                              |
| 25        | Clearly state the requirements that the model must follow in order to produce content, in the form of keywords, regulations, hints, or instructions.                                                                                                                                                                                    | Create a packing list for a beach vacation, including "sunscreen," "swimsuit," and "beach towel" as essential items.                                                                                                                                                                                                     |
| 26        | To write any text, such as an essay or paragraph, that is intended to be similar to a provided sample, include the following instructions:<br>- "Please use the same language based on the provided paragraph[ / title / text / essay / answer]".                                                                                       | "The gentle waves whispered tales of old to the silvery sands, each story a fleeting memory of epochs gone by." Please use the same language based on the provided text to portray a mountain's interaction with the wind.                                                                                               |
