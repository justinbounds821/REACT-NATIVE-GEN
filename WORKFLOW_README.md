# React Native Generator with Claude API - n8n Workflow

## Overview

This n8n workflow automatically generates complete React Native applications using Claude AI (Anthropic). It creates production-ready code with NativeWind (Tailwind CSS) styling, proper project structure, and all necessary configuration files.

## Features

### ✨ Key Improvements from Original

1. **Enhanced Error Handling**
   - Comprehensive error catching and user-friendly error messages
   - Validation for missing prompts
   - Proper error response node for failed requests

2. **Flexible Input Methods**
   - Direct prompt via webhook body
   - Google Docs integration for longer prompts
   - Query parameter support
   - Custom project naming

3. **Better Code Parsing**
   - Multiple file indicator patterns recognition
   - Improved code block extraction
   - Fallback mechanisms for unrecognized formats

4. **Complete Project Structure**
   - Full Expo setup with latest dependencies
   - TypeScript configuration included
   - ESLint and Prettier pre-configured
   - Testing setup with Jest
   - Comprehensive .gitignore

5. **Enhanced Response Format**
   - Files categorized by type (config, source, docs, assets)
   - Step-by-step setup instructions
   - Resource links for documentation
   - Metadata about generation

## Installation & Setup

### Prerequisites

1. **n8n instance** (self-hosted or cloud)
2. **Claude API Key** from Anthropic
3. **Google Docs access** (optional, for document-based prompts)

### Setup Steps

1. **Import the Workflow**
   - Copy the content from `react-native-generator-complete.json`
   - In n8n, go to Workflows → Import from File/URL
   - Paste the JSON content

2. **Configure Claude API Credentials**
   - In n8n, go to Credentials → Create New
   - Select "Header Auth"
   - Name it "Claude API Key"
   - Add header name: `x-api-key`
   - Add your Claude API key as the value

3. **Activate the Workflow**
   - Open the imported workflow
   - Click the "Active" toggle to enable it
   - Note the webhook URL displayed in the Webhook node

## Usage

### Method 1: Direct Prompt

Send a POST request to your webhook URL:

```bash
curl -X POST https://your-n8n-instance.com/webhook/generate-app \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "Create a todo list app with add, delete, and mark complete features",
    "projectName": "MyTodoApp"
  }'
```

### Method 2: Google Docs Prompt

For longer, more detailed prompts:

```bash
curl -X POST https://your-n8n-instance.com/webhook/generate-app \
  -H "Content-Type: application/json" \
  -d '{
    "useGoogleDoc": true,
    "googleDocId": "YOUR_GOOGLE_DOC_ID",
    "projectName": "MyComplexApp"
  }'
```

### Method 3: Query Parameters

```bash
curl -X POST "https://your-n8n-instance.com/webhook/generate-app?prompt=Create%20a%20weather%20app&projectName=WeatherApp"
```

## Workflow Structure

### Node Breakdown

1. **Webhook: Start Flow**
   - Receives HTTP POST requests
   - Endpoint: `/generate-app`

2. **Extract Parameters**
   - Extracts prompt, project name, and Google Doc settings
   - Handles both body and query parameters

3. **Check Google Doc**
   - Conditional node to determine input source

4. **Fetch Google Doc** (conditional)
   - Retrieves content from Google Docs if specified

5. **Merge Prompts**
   - Combines inputs and validates prompt presence

6. **Enhance Prompt**
   - Adds React Native best practices
   - Ensures NativeWind requirements
   - Adds project structure guidelines

7. **Claude API Call**
   - Sends enhanced prompt to Claude
   - Uses claude-3-opus model
   - 60-second timeout for complex requests

8. **Parse Claude Response**
   - Extracts code files from response
   - Identifies file names and content
   - Handles multiple code block formats

9. **Generate Project Structure**
   - Creates complete project scaffolding
   - Adds configuration files
   - Includes dependencies and scripts

10. **Prepare Final Response**
    - Organizes files by category
    - Adds setup instructions
    - Includes helpful resources

11. **Respond to Webhook**
    - Returns JSON response with all files

### Error Handling Path

- **Error Handler**: Catches any workflow failures
- **Error Response**: Returns structured error message

## Response Format

The workflow returns a JSON response with:

```json
{
  "success": true,
  "project": {
    "name": "MyApp",
    "totalFiles": 15,
    "totalAssets": 4,
    "generatedAt": "2024-01-01T00:00:00.000Z"
  },
  "message": "✅ React Native project \"MyApp\" generated successfully!",
  "filesByCategory": {
    "config": [...],
    "source": [...],
    "docs": [...],
    "assets": [...]
  },
  "files": [...],
  "setupInstructions": [...],
  "nativewindInfo": {...},
  "resources": {...},
  "metadata": {...}
}
```

## Generated Project Structure

```
MyApp/
├── assets/              # Image assets (placeholders)
├── components/          # Reusable components
├── screens/            # Screen components
├── App.js              # Main app component
├── app.json            # Expo configuration
├── babel.config.js     # Babel config with NativeWind
├── tailwind.config.js  # Tailwind CSS configuration
├── metro.config.js     # Metro bundler config
├── package.json        # Dependencies and scripts
├── tsconfig.json       # TypeScript configuration
├── .eslintrc.js        # ESLint rules
├── .prettierrc         # Prettier formatting
├── .gitignore          # Git ignore patterns
└── README.md           # Project documentation
```

## Customization

### Modify the Enhanced Prompt

Edit the "Enhance Prompt" node to add your specific requirements:
- Additional libraries
- Custom folder structure
- Specific coding standards
- UI/UX requirements

### Update Dependencies

Modify the "Generate Project Structure" node to:
- Add/remove npm packages
- Update version numbers
- Include additional config files

### Change Claude Model

In the "Claude API Call" node, you can change:
- Model: `claude-3-opus-20240229` to other available models
- Temperature: Adjust for more/less creative output
- Max tokens: Increase for larger projects

## Troubleshooting

### Common Issues

1. **"No prompt provided" error**
   - Ensure you're sending a prompt in the request body or via Google Doc
   - Check the JSON structure of your request

2. **Claude API errors**
   - Verify your API key is correctly configured
   - Check API rate limits
   - Ensure the prompt isn't too long

3. **File parsing issues**
   - The workflow handles multiple file formats
   - If files aren't detected, check Claude's response format

### Debug Mode

To debug the workflow:
1. Open the workflow in n8n
2. Click "Execute Workflow" manually
3. Use test data in the Webhook node
4. Step through each node to see outputs

## Best Practices

1. **Prompt Engineering**
   - Be specific about UI requirements
   - Mention any specific libraries needed
   - Describe user flows clearly

2. **Project Names**
   - Use alphanumeric characters
   - Avoid spaces (they'll be removed)
   - Keep it concise

3. **Google Docs Usage**
   - Make the document publicly accessible
   - Use plain text formatting
   - Structure with clear sections

## Security Notes

- API keys are stored securely in n8n credentials
- Webhook has no authentication by default (add if needed)
- Google Docs must be publicly readable if used
- Generated code is not automatically executed

## Support & Contribution

For issues or improvements:
1. Check the error response for debugging info
2. Review n8n logs for detailed errors
3. Modify the workflow nodes as needed
4. Test thoroughly before production use

## License

This workflow is provided as-is for use with n8n and Claude API.