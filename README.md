# Document-Analysis-using-LLMs
Document analysis refers to extracting, interpreting, and understanding the information contained within a document. 
# Introduction
 Traditionally, this involved manual review or simple keyword-based techniques, but with the rise of Large Language Models (LLMs) like GPT and BERT, LLMs are now preferred for document analysis because they can comprehend context, generate summaries, answer questions, and identify key insights efficiently. 
 <br>
 <br>
 Step 1: Extract Text from the PDF
 <br>
The first step in document analysis is extracting the content from a PDF file. We can use libraries like pdfplumber to open and read the text from each page of the PDF and save it into a .txt file for further analysis. You can install pdfplumber on your Python environment using the command: pip install pdfplumber.
<br>
<br>
Step 2: Preview the Extracted Text
<br>
After extracting the text, it’s essential to preview the content to ensure everything is correctly captured.
<br>
<br>
Step 3: Summarize the Document
<br>
To get a high-level overview of the document, you can use a pre-trained summarization model like t5-small. This allows you to condense large pieces of text into shorter summaries, which helps you to grasp the most important information. 
<br>
The pipeline(“summarization”, model= “t5-small”) sets up the summarization model using T5-small, a pre-trained transformer model designed for text summarization. The document_text[:1000] specifies the portion of the text to summarize (the first 1000 characters), while max_length = 150 and min_length = 30 control the maximum and minimum length of the summary in tokens. The do_sample = False parameter ensures deterministic output, meaning the model will not randomly sample from possible summaries but will give the same result every time.
<br>
<br>
Step 4: Split the Document into Sentences and Passages
<br>
For more detailed analysis, like question generation, it’s important to split the document into smaller chunks. This step tokenizes the document into sentences and combines them into manageable passages for subsequent steps.
<br>
<br>
Step 5: Generate Questions from the Passages Using LLMs
<br>
The next step is to generate questions based on the document’s content. This helps in understanding key information points and can be used to check the comprehension of the document.
<br>
<br>
Step 6: Answer the Generated Questions Using a QA Model
<br>
After generating the questions, we can use a pre-trained question-answering (QA) model to find the answers within the text. The deepset/roberta-base-squad2 model extracts answers based on the context of the passage.

# Features
Google terms and services dataset

# Conclusion
We used a question-answering (QA) pipeline with the deepset/roberta-base-squad2 model to answer questions generated from the document passages. The function answer_unique_questions() tracks unique questions in a set to ensure it answers each question only once. As the code processes each passage, it checks whether it has already answered a question; if not, it generates an answer based on the passage’s context. This avoids answering duplicate questions and ensures efficient processing of all relevant queries. So, this is how we can analyze documents using LLMs step-by-step. LLMs excel at understanding natural language, which makes them ideal for handling complex documents and extracting meaningful insights with high accuracy and minimal human intervention. 

# Contributing
If you are interested in contributing to the project, please create a fork of the repository and submit a pull request. All contributions are welcome and appreciated.
