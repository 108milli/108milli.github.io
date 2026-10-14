# Extra TLC Oil website starter

This is a static, mobile-responsive product website starter for Extra TLC Oil.

## Included
- `index.html`: page content, SEO metadata and product structured data
- `styles.css`: blush/ivory, botanical luxury visual design
- `script.js`: small JavaScript file for future enhancements
- `images/`: the two product images currently available in this conversation
- `media/`: folder for future videos
- `robots.txt` and `sitemap.xml`: starter SEO files (update the domain after deployment)

## Before publishing
1. Open `index.html` using GitHub's web editor.
2. Find every occurrence of `YOUR_INSTAGRAM_HANDLE` and replace it with the real Instagram username (without the @).
3. After deployment, replace `YOUR-PROJECT.pages.dev` in the canonical URL and Open Graph URL with the actual live site address.
4. Confirm product size, price, availability and ingredient wording. The page currently uses ₹800 and 100 ml from the supplied artwork; confirm these are current.
5. The introductory offer is not represented as a guaranteed live discount. Update it only after confirming its terms.
6. Review all product and marketing claims for accuracy before publishing.

## Add more photos
1. In the GitHub repository, open the `images` folder.
2. Select **Add file → Upload files**.
3. Upload your image, preferably compressed WebP/JPG and under 5 MB.
4. To display it, open `index.html` and find `id="image-gallery"`.
5. Duplicate a `<figure>...</figure>` block and update the image filename and alt text.
6. Commit the change. Cloudflare Pages will redeploy automatically.

Example gallery item:
```html
<figure>
  <img src="images/new-product-photo.webp" alt="Accurate description of the product photo" loading="lazy">
  <figcaption>Short image caption</figcaption>
</figure>
```

## Add a video
For browser-uploaded videos, GitHub's web interface has per-file size limits. For larger videos, host the video on a video service and embed it, or use a suitable object-storage/video-hosting service. Avoid committing large videos to GitHub.

If a video file is small enough and you want to store it in the repository:
1. Upload it to `media/`.
2. In `index.html`, replace one `.video-placeholder` block with:
```html
<article class="video-card">
  <video controls playsinline preload="metadata" poster="images/extra-tlc-massage-oil1.jpg">
    <source src="media/product-demo.mp4" type="video/mp4">
    Your browser does not support embedded video.
  </video>
  <h4>Product demonstration</h4>
  <p>A short, accurate description of this video.</p>
</article>
```
3. Add this style to `styles.css` if you use the video card:
```css
.video-card { background: #fffaf6; border: 1px solid #e6d5ca; padding: 10px; }
.video-card video { width: 100%; display: block; aspect-ratio: 9 / 16; background: #eee; }
.video-card h4 { font-family: "Playfair Display", Georgia, serif; font-weight: 400; }
```
4. Commit the change.

For customer feedback videos, get the customer's explicit permission before publishing their face, name, voice or testimonial. Use real reviews only.

## Publish through Cloudflare Pages
1. Create a GitHub repository named `extra-tlc-oil-website`.
2. Upload all files and folders from this package to the repository's root (so `index.html` is at the top level).
3. Create/sign in to a Cloudflare account.
4. Open **Workers & Pages → Create application → Pages → Connect to Git**.
5. Connect GitHub and select `extra-tlc-oil-website`.
6. For a plain HTML website, use:
   - Production branch: `main`
   - Framework preset: `None` / no framework
   - Build command: `exit 0` (or leave empty if the UI allows it)
   - Build output directory: `/` or the repository root, depending on the UI's accepted value
7. Deploy. Cloudflare will show the live `pages.dev` URL.
8. Replace the placeholder domain in the SEO tags, test all links and check the page on mobile.

## Browser upload limits
GitHub's browser upload supports up to 100 files at once, with a per-file limit of 25 MiB. Keep repository videos small; external video hosting is usually better for performance and repository size.
