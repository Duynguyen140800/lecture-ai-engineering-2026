# 第1回 解答

## 演習

- 講座に固有の質問（宿題の3レベル）へのモデルの回答（要約でよい）：
- 用語集の正しい意味と比べて気づいたこと：
- 表示できたトークン数（入力 / 出力）：

## 宿題

- 取り組んだレベル：発展
- やったこと：I run the 2 questions (3 times per each) each while changing the model (AIE_MODEL env var). Modify the codes which help me ask follow-up questions while keeping the conversation history. I added codes to measure response time and display input and output token counts, then I compared gemini-3.5-flash-lite and gemini-3.8-flash using two prompts: a one-sentence explanation of LoRA and an approximately 200-word explanation.
- 結果：Gemini 3.8 Flash produced more output tokens and had higher average response times for both prompts in this experiment. However, response times varied substantially. Repeated 503 errors usually appear with Gemini 3.8 Flash
- 気づき・疑問：Longer prompts increased input tokens from 8 to 26 and produced substantially more output tokens. However, output length alone did not explain response time: some short answers took much longer than others. The measurements represent elapsed API-call time, rather than model computation alone.
I think that free-tier limits involve requests per minute, input tokens per minute, and requests per day, with limits depending on the model and project tier. Repeated experiments consume request allowance, while longer prompts and conversation histories increase input-token usage. The higher-tier model will use more tokens and usually appears with a 503 error.
