# langchain-selenium-browser

A langchain web browser tool based on Selenium

## Usage:
```javascript
    const WebBrowser = require('langchain-selenium-browser')

    const model = new ChatOpenAI({
        openAIApiKey: process.env.OPENAI_API_KEY,
        temperature: 0.9,
    });
    const embeddings = new OpenAIEmbeddings({
        openAIApiKey: process.env.OPENAI_API_KEY,
    });

    const webBrowserTool = new WebBrowser({
        model: model,
        embeddings: embeddings,
        seleniumDriverOptions: {
            browserName: 'chrome',
        }
    })
```