Japan Prefecture Selector
==========================

Single-file static interactive site to select prefectures on a map of Japan.

Files
- index.html : Single-file site (HTML, CSS, JS) with an inline SVG map.
- map-full.svg : SVG map of Japan from [japanese-prefectures](https://github.com/geolonia/japanese-prefectures/).

Features
- Click or keyboard-activate prefectures to toggle selection.
- Selected prefectures are colored and listed in the sidebar.
- Saves click state to local storage.
- Can be printed out.

Hosting on S3 (quick steps)

1. Create an S3 bucket and enable static website hosting (replace BUCKET_NAME):

   ```bash
   aws s3 mb s3://BUCKET_NAME
   aws s3 website s3://BUCKET_NAME --index-document index.html
   ```

2. Upload the file and set public-read (or use a bucket policy):

   ```bash
   aws s3 cp index.html s3://BUCKET_NAME/index.html --acl public-read
   aws s3 cp full-map.svg s3://BUCKET_NAME/full-map.svg --acl public-read
   ```

3. The website will be available at: http://BUCKET_NAME.s3-website-<region>.amazonaws.com/

License
- GFDL since the svg file is GFDL from [japanese-prefectures](https://github.com/geolonia/japanese-prefectures/).