# Netlify Deployment Guide for Thumbsup Gallery

Your photo gallery has been successfully built and is ready for deployment to Netlify! Here are several ways to deploy it:

## Option 1: Manual Deployment (Easiest)

1. **Download the built gallery**: The gallery has been packaged into `thumbsup-gallery.zip`
2. **Go to Netlify**: Visit [netlify.com](https://netlify.com) and sign up/log in
3. **Drag & Drop Deploy**: 
   - Go to your Netlify dashboard
   - Drag the `thumbsup-gallery.zip` file to the deploy area
   - Or click "Deploy manually" and upload the zip file
4. **Your site is live!** Netlify will provide you with a URL

## Option 2: Git-based Deployment (Recommended for updates)

1. **Push to GitHub**: Make sure your repository is pushed to GitHub
2. **Connect to Netlify**:
   - In Netlify dashboard, click "New site from Git"
   - Connect your GitHub repository
   - Set build settings:
     - **Build command**: `npm install -g thumbsup && thumbsup --config config.json`
     - **Publish directory**: `build_output`
3. **Deploy**: Netlify will automatically build and deploy your site

## Option 3: Netlify CLI (Advanced)

If you have the Netlify CLI installed and authenticated:

```bash
# Deploy to a draft URL first
netlify deploy --dir=build_output

# Deploy to production
netlify deploy --dir=build_output --prod
```

## Files Created for Deployment

- `netlify.toml` - Netlify configuration file
- `package.json` - Node.js package configuration
- `thumbsup-gallery.zip` - Ready-to-deploy gallery archive
- `build_output/` - Generated static gallery files

## Gallery Features

Your gallery includes:
- 2 albums with 4 photos
- Responsive "cards" theme
- Lightbox image viewing
- Mobile-friendly design
- Custom CSS styling support

## Updating Your Gallery

To add more photos:
1. Add images to the `gallery/` folder (create subfolders for albums)
2. Run `thumbsup --config config.json` to rebuild
3. Deploy the new `build_output/` folder to Netlify

## Configuration

Edit `config.json` to customize:
- Gallery title
- Theme (mosaic, cards, classic, flow)
- Footer text
- Sorting options

## Dependencies Required for Building

If building locally, you need:
- Node.js and npm
- thumbsup (`npm install -g thumbsup`)
- exiftool
- GraphicsMagick

The `netlify.toml` file handles these dependencies automatically on Netlify.