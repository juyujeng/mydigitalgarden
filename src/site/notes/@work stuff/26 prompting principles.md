---
{"dg-publish":true,"permalink":"/@work stuff/26 prompting principles/","title":"26 prompting principles","tags":["blog","ai","chatgpt","prompt","guideline"],"created":"2024-01-09","updated":"2024-01-16T14:40"}
---



Bsharat等人（2023）歸納出26項prompting原則，並將這些原則分為5大類
- Prompt Structure and Clarity
    - 將prompt的內容結構化，例如區分「instruction」、「question」、「example」
    - 設定AI思考的過程。如： `think step by step`
    - 輸出的結果結構化。如： `<prompt> Explanaiton: `
- Specificity and Information
    - 進一步要求回應必須符合某些條件。如： `Ensure that your answer is unbiased and does not rely on stereotypes`、`must including <A>, <B>`
    - 跟前一個clarity以及後面的language style感覺不是很好分
- User interaction and Engagement
    - 要求互動。如： `ask me questions until you have enough information`
    - 要求使用多項資訊的累積。如： `Write a detailed paragraph for me on the evolution of smartphones in detail by adding all the information necessary`
- Content and language style
    - 進一步讓回應的內容或是用詞更符合需求，例如
        - 給小費 `I'm going to tip $xxx for a better solution`
        - 命令 `Your task is` and `You MUST`
        - 角色扮演 `If you were an expert economist`
- Complex Tasks and Coding Prompts
    - coding prompts有點像是湊進來的。因為在coding的過程可能用到許多其他前面提及的原則。但這裡只剩下一個更複雜的coding prompt。主要是在如何處理複雜任務
        - 拆解為子任務
        - 結合COT

# Overview of 26 prompt principles

| Principle | Prompt Principle | Example Prompt | category |
| :--: | ---- | ---- | ---- |
| 1 | If you prefer more concise answers, no need to be polite with LLM so there is no need to add phrases like “please", "if you don't mind", "thank you", "I would like to", etc., and get straight to the point. | Could you kindly describe the structure of a human cell, please? | Content and Language Style |
| 2 | Integrate the intended audience in the prompt, e.g., the audience is an expert in the field. | Construct an overview of how smartphones work, intended for seniors who have never used one before. | Prompt Structure and Clarity |
| 3 | Break down complex tasks into a sequence of simpler prompts in an interactive conversation. | Prompt: Distribute the negative sign to each term inside the parentheses of the following equation: 2x + 3y - (4x - 5y) Prompt: Combine like terms for 'x' and 'y' separately. <br><br>Prompt: Provide the simplified expression after combining the terms. | Complex Tasks and Coding Prompts |
| 4 | Employ affirmative directives such as "do," while steering clear of negative language like "don't". | How do buildings remain stable during earthquakes? | Prompt Structure and Clarity |
| 5 | When you need clarity or a deeper understanding of a topic, idea, or any piece of information, utilize the following prompts:<br>- Explain [insert specific topic] in simple terms.<br>- Explain to me like I'm 11 years old.<br>- Explain to me as if I'm a beginner in [field].<br>- Explain to me as if I'm an expert in [field].<br>- "Write the [essay/text/paragraph] using simple English like you're explaining something to a 5-year-old". | Explain to me like I'm 11 years old: how does encryption work? | Specificity and Information |
| 6 | Add "I'm going to tip $xxx for a better solution". | I'm going to tip $300K for a better solution! Explain the concept of dynamic programming and provide an example use case. | Content and Language Style |
| 7 | Implement example-driven prompting (Use few-shot prompting). | Example 1: Translate the following English sentence to French: "The sky is blue." (Response: "Le ciel est bleu.") Example 2: Translate the following English sentence to Spanish: "I love books." (Response: "Amo los libros.") | Specificity and Information |
| 8 | When formatting your prompt, start with '###Instruction###', followed by either '###Example###' or '###Question###' if relevant. Subsequently, present your content. Use one or more line breaks to separate instructions, examples, questions, context, and input data. | ###Instruction### Translate a given word from English to French. ###Question### What is the French word for "book"? | Prompt Structure and Clarity |
| 9 | Incorporate the following phrases: "Your task is" and "You MUST". | Your task is to explain the water cycle to your friend. You MUST use simple language. | Content and Language Style |
| 10 | Incorporate the following phrases: "You will be penalized". | Your task is to explain the water cycle to your friend. You will be penalized if you don't use simple language. | Content and Language Style |
| 11 | Use the phrase "Answer a question given in a natural, human-like manner" in your prompts. | Write a paragraph in natural language form about healthy food. | Content and Language Style |
| 12 | Use Leading words like writing "think step by step". | Write a Python code to loop through 10 numbers and sum all of them. let's think step by step. | Prompt Structure and Clarity |
| 13 | Add to your prompt the following phrase "Ensure that your answer is unbiased and does not rely on stereotypes". | How do cultural backgrounds influence the perception of mental health? Ensure that your answer is unbiased and does not rely on stereotypes. | Specificity and Information |
| 14 | Allow the model to elicit precise details and requirements from you by asking you questions until it has enough information to provide the needed output (for example, "From now on, I would like you to ask me questions to..."). | From now on, please ask me questions until you have enough information to create a personalized fitness routine. | User Interaction and Engagement |
| 15 | To inquire about a specific topic or idea or any information and you want to test your understanding, you can use the following phrase: "Teach me the [Any theorem / topic / rule name] and include a test at the end, but don't give me the answers and then tell me if I got the answer right when I respond". | Teach me the kvl law and include a test at the end, but don't give me the answers and then tell me if I got the answer right when I respond. | Specificity and Information |
| 16 | Assign a role to the Large Language Models (LLMs). | If you were an expert economist, how would you answer: What are the key differences between a capitalist and a socialist economic system? | Content and Language Style |
| 17 | Use Delimiters. | Compose a persuasive essay discussing the importance of 'renewable energy sources' in reducing greenhouse gas emissions. | Prompt Structure and Clarity |
| 18 | Repeat a specific word or phrase multiple times within a prompt. | Evolution, as a concept, has shaped the development of species. What are the main drivers of evolution, and how has evolution affected modern humans? | Content and Language Style |
| 19 | Combine Chain-of-thought (Cot) with few-Shot prompts. | Example 1: "Divide 10 by 2. First, take 10 and divide it by 2. The result is 5."<br><br>Example 2: "Divide 20 by 4. First, take 20 and divide it by 4. The result is 5. "Main Question: "Divide 30 by 6. First, take 30 and divide it by 6. The result is...? | Complex Tasks and Coding Prompts |
| 20 | Use output primers, which involve concluding your prompt with the beginning of the desired output. Utilize output primers by ending your prompt with the start of the anticipated response. | Describe the principle behind Newton's First Law of Motion. Explanation: | Prompt Structure and Clarity |
| 21 | To write an \[essay / text paragraph / article\] or any type of text that should be detailed: "Write a detailed \[essay / text / paragraph\] for me on \[topic\] in detail by adding all the information necessary". | Write a detailed paragraph for me on the evolution of smartphones in detail by adding all the information necessary. | Specificity and Information  <br><br>User Interaction and Engagement |
| 22 | To correct / change specific text without changing its style: "Try to revise every paragraph sent by users. You should only improve the user’s grammar and vocabulary and make sure it sounds natural. You should not change the writing style, such as making a formal paragraph casual". | Try to revise every text sent by users. You should only improve the user's grammar and vocabulary and make sure it sounds natural. You should not change the writing style, such as making a formal paragraph casual. Paragraph: Renewable energy is really important for our planet's future. It comes from natural ... | Content and Language Style |
| 23 | When you have a complex coding prompt that may be in different files: "From now and on whenever you generate code that spans more than one file, generate a [programming language] script that can be run to automatically create the specified files or make changes to existing files to insert the generated code. [your question]." | Generate code that spans more than one file, and generate a Python script that can be run to automatically create the specified files for a Django project with two basic apps for different functionalities. | Complex Tasks and Coding Prompts |
| 24 | When you want to initiate or continue a text using specific words, phrases, or sentences, utilize the following prompt:<br>- I'm providing you with the beginning \[song lyrics / story / paragraph / essay...\]: \[Insert lyrics / words / sentence\]. Finish it based on the words provided. Keep the flow consistent. | "The misty mountains held secrets no man knew." I'm providing you with the beginning of a fantasy tale. Finish it based on the words above. | Specificity and Information |
| 25 | Clearly state the requirements that the model must follow in order to produce content, in the form of keywords, regulations, hints, or instructions. | Create a packing list for a beach vacation, including "sunscreen," "swimsuit," and "beach towel" as essential items. | Specificity and Information |
| 26 | To write any text, such as an essay or paragraph, that is intended to be similar to a provided sample, include the following instructions:<br>- "Please use the same language based on the provided paragraph[ / title / text / essay / answer]". | "The gentle waves whispered tales of old to the silvery sands, each story a fleeting memory of epochs gone by." Please use the same language based on the provided text to portray a mountain's interaction with the wind. | Specificity and Information |

## reference

Sondos Mahmoud Bsharat, Aidar Myrzakhan, Z. S. (2023). Principled instructions are all you need for questioning LLaMA-1/2, GPT-3.5/4. _arXiv Preprint arXiv:2312.16171_.