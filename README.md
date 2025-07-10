# LLM Engineering - Exploring LLMs

## Framewors
 - OpenAI
 - Ollama
 - HugingFace
 - BeautifulSoup - html parser

## Projects

### Day 5 project: Company brochure. 
Build an assistant that analyzes the contents of several relevant pages from a company website 
and creates a short brochure about the company for prospective customers, investors and recruits. Respond in markdown. Include details of company culture, customers and careers/jobs if you have the information. 

In this exersise we are using multipe LLM calls and orchestrating them using openai. One call for checking the relevant links and another call for creating the brochure.
Using BeautifulSoup html parser
Using OpenAI for reasoning the most relevant link and for creating final brochure

Remarks:
We created a brochure for hugging face by scraping the landing page and relevant links. 
create_brochure("HuggingFace", "https://huggingface.co")

We can stream the response by enbling flag as follow:
    stream = openai.chat.completions.create(
        model=MODEL,
        messages=[
            {"role": "system", "content": system_prompt},
            {"role": "user", "content": get_brochure_user_prompt(company_name, url)}
          ],
        stream=True
    )