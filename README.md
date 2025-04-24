# Heroku Buildpack: Tesseract 5.5.0

Installs Tesseract 5.5.0 + Leptonica 1.85.0 and English `eng.traineddata` for OCR on Heroku.

## Usage

1. In your Heroku app repository run:
   
   ```bash
   heroku buildpacks:clear  
   heroku buildpacks:add --index 1 https://github.com/YOUR-ORG/tesseract-buildpack.git  
   heroku buildpacks:add --index 2 heroku/ruby
   ```

2. Deploy as usual. Your Ruby app using RTesseract & MiniMagick will then have:
   - `tesseract` in its `$PATH`
   - Leptonica-powered image support (JPG, PNG, TIFF)
   - English `eng.traineddata` for best-accuracy OCR

## Environment Variables

This buildpack sets:

- PATH=/app/vendor/bin:$PATH  
- LD_LIBRARY_PATH=/app/vendor/lib:$LD_LIBRARY_PATH  
- TESSDATA_PREFIX=/app/vendor/share/tessdata  

