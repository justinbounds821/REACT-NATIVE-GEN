# Quick Start Guide - React Native Generator

## 🚀 5-Minute Setup

### 1. Import Workflow
1. Copy all content from `react-native-generator-complete.json`
2. In n8n: **Workflows** → **Add Workflow** → **Import from URL or paste JSON**
3. Paste and click **Import**

### 2. Add Claude API Key
1. Go to **Credentials** → **Create New**
2. Search for **Header Auth**
3. Configure:
   - **Name**: `Claude API Key`
   - **Header Name**: `x-api-key`
   - **Header Value**: `[Your Claude API key]`
4. Click **Save**

### 3. Activate Workflow
1. Open the imported workflow
2. Toggle **Active** switch (top bar)
3. Copy the webhook URL from the first node

## 🎯 First Test

Run this command (replace URL with your webhook URL):

```bash
curl -X POST https://your-n8n.com/webhook/generate-app \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "Create a simple counter app with increment and decrement buttons",
    "projectName": "CounterApp"
  }'
```

## 📱 What You'll Get

The response includes:
- Complete React Native project files
- All configurations (Expo, NativeWind, ESLint)
- Setup instructions
- Ready-to-run code

## 🛠 Next Steps

1. Save all files from the response to a new folder
2. Run `npm install`
3. Run `npm start`
4. Press `i` for iOS or `a` for Android

## 💡 Pro Tips

- **Better Results**: Use detailed prompts (see `example-prompts.md`)
- **Long Prompts**: Use Google Docs integration
- **Debug**: Check workflow execution in n8n UI
- **Customize**: Edit the "Enhance Prompt" node for specific requirements

## 🆘 Troubleshooting

| Issue | Solution |
|-------|----------|
| No response | Check webhook URL is correct |
| API error | Verify Claude API key in credentials |
| Empty files | Check prompt is not empty |
| Timeout | Prompt might be too complex, simplify |

## 📚 Resources

- Full documentation: `WORKFLOW_README.md`
- Example prompts: `example-prompts.md`
- Claude API: https://console.anthropic.com/

---

**Ready to generate your first React Native app? Try the examples in `example-prompts.md`!** 🎉