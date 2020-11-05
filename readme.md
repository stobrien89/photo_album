# Photo Album Sample Project

## Setting up

1. Before running the sample, copy the Environment variable configuration parameters from Cloudinary's [Management Console](https://cloudinary.com/console) of your account into `.env` file of the project or export it (i.e. export CLOUDINARY_URL=xxx).
1. In the project directory, run `npm install` to install all the required dependencies.
1. Run `npm start` to start the server , if you want to run a
   development mode server (autoreload) run `node run-script debug`.
1. Open the sample page in a browser: http://localhost:9000

## Steps taken:

### 1. Limiting image size upon upload:

    #### Direct signed/unsigned client-side upload

    - Added blueimp file upload and jQuery/jQueryui
    - Adjusted/uncommented script tags in unsigned/signed direct upload views
    - Set maxWidth and maxHeight to 500, but those properties appear to constrict size to one pixel less than the given value (501 x 501 would be most precise).

    #### Server-side upload

    - Added width/height properties and crop of "limit" via the upload API

### 2. Tagging uploaded images

- Added server-side upload tag (for server uploads) via the upload API.
- For client-side signed/unsigned direct uploads, I added a tag that is attached via the client, as well as another tag that is attached via the server (visible when the photo is viewed in the cloudinary dashboard).

### 3. Thumbnail Transformations

- Added two separate thumbnails with multiple properties (formated in an array of transformation objects separated by transformation type).

### 4. Adding Delete Button

- Added form with delete button
- Adjusted Method Override to accept ("\_method") format. For no reason really, it's just what I'm accustomed to.
- Added delete route/method to controller.
- 'Juggled' around with jugglingdb for a bit until I figured out the right sequence of methods to delete a single record.
