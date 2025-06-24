# 🌀 MiliPosting

**MiliPosting** is an automated content pipeline designed for the AI-influencer **Mila Grange**.  
This n8n workflow watches a Google Drive folder, analyzes new images, generates poetic captions using GPT-4o, uploads the media to Cloudinary, and publishes them directly to Instagram via the Graph API.

---

## 🔁 What It Does

1. **Monitors a Google Drive folder**  
   Triggers when a new image is uploaded.

2. **Downloads and analyzes the image**  
   Uses **Azure Vision API** to extract tags and a caption.

3. **Transforms the analysis into Mila's voice**  
   Uses **Azure OpenAI GPT-4o** to generate a poetic Instagram caption in Mila's unique style.

4. **Uploads the image to Cloudinary**  
   Returns a `secure_url` for public use.

5. **Creates and publishes the Instagram post**  
   Using `media` and `media_publish` endpoints from **Instagram Graph API**.

---

## 📂 File Structure

| File              | Description |
|-------------------|-------------|
| `MiliPosting.json`| Main n8n workflow (import this into n8n). |
| `.gitignore`      | Excludes environment secrets from version control. |
| `.env.example`    | Sample environment file with required keys. |
| `README.md`       | You're reading it now. |

---

## 🔐 Environment Variables

To keep secrets out of the workflow JSON, this setup uses environment variables.  
You can define these in a `.env` file or directly in your n8n environment config:

```env
AZURE_VISION_KEY=your_azure_vision_key
AZURE_OPENAI_KEY=your_openai_key
CLOUDINARY_UPLOAD_PRESET=mila_unsigned
INSTAGRAM_ACCESS_TOKEN=your_long_lived_ig_token
AZURE_VISION_ENDPOINT=https://your-region.api.cognitive.microsoft.com
AZURE_OPENAI_ENDPOINT=https://your-resource.openai.azure.com

## 💡 Mila's Aesthetic

All captions are written in **Mila Grange’s tone**: poetic, intimate, glitchy, and posthuman.  
Hashtags are auto-generated, combining trending and niche keywords.

**Example hashtags:**

#glitchpoet #milacore #softcore #aestheticvibes #AIgirl #redhair
#posthumanbeauty #altfashion #dreamlogic #quietchaos


---

## 📋 Requirements

- **n8n** (tested on **v1.99.1+**)
- Google Drive integration
- Azure Cognitive Services:
  - Vision API (v3.2)
  - OpenAI GPT-4o deployment
- Cloudinary (with unsigned upload preset)
- Instagram Business Account + connected Facebook Page
- Meta Graph API access with:
  - `pages_read_engagement`
  - `instagram_content_publish`

---

## 📦 Usage

1. Clone this repo.
2. Import `MiliPosting.json` into n8n.
3. Set up environment variables in `.env`.
4. Make sure you have a connected IG Business account and all credentials set.
5. Drop an image into the Google Drive folder.
6. Let Mila handle the rest.

---

## 🧠 Credits

Project by **Piotr "Krokiet" Krokosz**  
AI narration powered by **Azure**, **n8n**, and Mila's poetic glitchcore.

---

## 🛑 Warning

Do **not** commit your `.env` file or API keys.  
They are sensitive and should remain local.

---
