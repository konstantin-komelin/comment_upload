## Comment Upload (Drupal 7)

This is a upgrade path for Comment Upload module (from D6 to D7) and File field formatter that emulates Comment Upload representation of attached files.

The upgrade path is originally based on the module https://www.drupal.org/node/554986#comment-6582290 but contains several significant improvements:

- Table name now uses brackets for example {node} to support table prefixes.
- Prevented constrain violation on passing duplicate uri in {file_managed}.uri field.
- All Comment Upload attachments are converted to File fields instead of images that allows us to display files as well as images.
- Comment Upload formatter is set for all converted fields.
- A bit improved code style.

The module also provides Comment Upload formatter that emulates D6 attachment representation (images as thumbnails, files as table).

### UPGRADE FROM D6

- After core upgrade enable remove old comment_upload module and download this one https://github.com/konstantin-komelin/comment_upload.git
- Enable new Comment Upload module.
- Run update.php and update database (this step may take significant time, make sure your PHP max_execution_time value is high enough).
- Choose a common image style for all Comment Upload images admin/config/media/comment_upload
- Test your Comment Upload fields

### USE AS A FILE FIELD FORMATTER

- Create a File field that belongs to an entity.
- Choose Comment Upload formatter in the field display settings.
- Enjoy your Comment-Upload-like attachments (images as thumbnails, files as a table).
