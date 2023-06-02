# langchain-selenium-browser

A langchain web browser tool based on Selenium

## Usage:
```javascript
    const WebBrowserToolKit = require('@agent-mimir/selenium-browser').WebBrowserToolKit;
    const model = new ChatOpenAI({
        openAIApiKey: process.env.OPENAI_API_KEY,
        temperature: 0.9,
    });
    const embeddings = new OpenAIEmbeddings({
        openAIApiKey: process.env.OPENAI_API_KEY,
    });

    const webToolKit = new WebBrowserToolKit({
        browserConfig: {
            browserName: "chrome", // chrome, firefox, edge
            disableHeadless: false // set to true to see the browser, false by default
        },
        maximumChunkSize: 3000, // size of chunks to split the website content into, defaults to 3000
        numberOfRelevantDocuments: 2, // Max number of chunks to use when analyzing a website page, defaults to 2,  set to 'all' to use all chunks (slow)
    }, model, embeddings);

    //Add to agents tool:
    tools: [
            ...webToolKit.tools,
        ],
```