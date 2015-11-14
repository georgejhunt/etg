#Description of the desired system
Purpose:  to collect, and present to customers, detailed information and pictures of furniture that is available for sale at ETG Furniture Store at 17 Brook in Staten Island.
What computer hardware will be used for the application?
  The application will run on a computer in the cloud. The only requirement for local computers at ETG Furniture Store is that they be able to run a current version of firefox or chrome.
What information will be collected?
  Lot.line
  Set number
  material
  dimension
  location
  price
  category/classification
How are the pictures associated with items?
  After the above information is entered into the database, price tags are printed at the store for a specific lot. Each price tag includes a barcode which uniquely identifies the item.
  Photogrphs, with unique file names, are synchronized with the information already entered into the database by, in every case, first making a photograph of the barcode. The photographs are sequentially uploaded to an appliction which uses the barcode to link each of the subsequent photos with the item that has been identified by the barcode.
What provision for editing, reordeering, deleting, must be made for photos that are uploaded to the barcode recognition service?
How will information about items for sale be presented to the customers' device?
The device will have branding and direct access buttoms at the top and bottom of the screen, and an array of pictures in the middle region. Swiping vertically will scroll through available items, and horizontally will expose additional images related to a specific item.
  Items will, in general, be presented in the order they arrived in the store, with the most recent, first. The search function will accept a large number of potential search words, which all get resolved to major categories (mapping is yet to be determined) and are returned in "most recent" first order.
What resources are currently in place that might be helpful as models, or code snippets, to aid development of this project?
The data collection is currently done by filemaker. The current thinking is that the whole filemaker application can be replaced by a single data colection screen. The barcode image recognition, uploading, reviewing, editing is currently implemented in php/mysql, and may be appropriate for reuse.
  The display and output code, with thumbnails branching to detailed item information, is not appropriate for hand held devices, and needs to be replaced.

