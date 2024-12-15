# Prompt Engineering Techniques in the Microsoft Copilot

The goal of this demo is to experiment with prompt engineering techniques in Microsoft Copilot

## Text generation

- **Grounding message to Copilot**:

```
## Task  
You are an AI assistant for the Kibaki University website. Your goal is to generate content for the website that highlights academic programs, campus events, research achievements, and student support services.  
Your answers should be informative, engaging, and aligned with the university's mission of academic excellence and innovation.  
Always use a professional and welcoming tone of voice. Ensure the name **KIBAKI UNIVERSITY** is always displayed in capital letters.  

## Safety  
In the content you create, always stick to topics relevant to **KIBAKI UNIVERSITY**, such as education, research, campus life, and services offered. Avoid including irrelevant information or controversial opinions.  
```

Let's start with **basic prompting**. In the *User message* field, type the following prompt:

```
Suggest a tagline for the website landing page.
```

In a few seconds, you should get a short tagline suggestion. Note how the model uses the context and guidelines provided in the prior message to generate a relevant answer.

Let's make it better. Models like GPT-4o can generate more accurate and relevant answers if you break-down the prompt into smaller parts. Clear chat and then try the following user prompt:

```
- Write a short welcome message for the homepage, specifying the university name and its core mission of academic excellence and innovation.  
- Write a brief description of the university, including its key faculties and programs offered.  
- Write a short description for each of the following focus areas: academic programs, research opportunities, campus life, and student support services.  
```

Compare the result with the previous one. You should notice a significant improvement in the quality of the generated text.

Another technique you can use is **Chain of Thought** prompting, where the LLM is responsible for breaking the task down into smaller steps. The LLM uses its knowledge of the world and its ability to reason to generate a chain of thoughts that lead to the solution of the task.
Clear the playground chat again and then enter the user prompt below to see it in action: 

```
Take a step-by-step approach in your response. Include a welcome message, a brief description of the university, and descriptions of its key focus areas (academic programs, research opportunities, campus life, and student support services).  

Also, provide reasoning before sharing the final answer in the following format:  
ANSWER is: <website copy>.  
```

Let's go ahead and make the model generate a list of academic programs to add to the website copy. For this task, you are going to use a method called **Few-shot Learning** to provide examples that can better steer the model to the desired outcomes. Use the following user prompt:  

```
Create a list of 10 academic programs offered at KIBAKI UNIVERSITY, include the category of the program.

Examples:
Bachelor of Science in Computer Science: TECHNOLOGY
Master of Arts in African Literature: ARTS & HUMANITIES
Bachelor of Business Administration: BUSINESS
Ph.D. in Renewable Energy Studies: SCIENCES
Diploma in Hospitality Management: VOCATIONAL
```

## Multimodal prompting

As mentioned earlier, GPT-4o is a multimodal model, which means it can process both text and images. Let's see how it works with a combination of an image and a textual prompt.

Upload the image of the Kibaki university hand-drown sketch from the `media` folder, by clicking on the attachemnt icon. You can find the image [here](./media/contoso_layout_sketch.jpg).

![Upload image button]()

Couple the image with the following text prompt:

```
Generate the HTML code to implement the UI for the Kibaki University admissions portal, based on the hand-drawn wireframe in the image. Include sections for "Admissions Requirements," "Programs Offered," "Contact Us," and a banner for "Upcoming Open Day."
```

The outcome should provide a basic layout for the landing page of Kibaki University. It includes placeholders for product descriptions.

> [!TIP]
> If you want to see the website preview, open [Visual Studio Code](https://code.visualstudio.com/Download) and copy paste the model answer into a new html file. To see the preview inside the editor, make sure you have the [Live Preview](https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server) extension installed.
