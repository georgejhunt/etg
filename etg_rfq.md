#Description of the desired system

##Purpose:

to collect, and present to customers, detailed information and pictures of furniture that is available for sale at ETG Furniture Store at 17 Brook in Staten Island.

####What computer hardware will be used for the application?

  The application will run on a computer in the cloud. The only requirement for local computers at ETG Furniture Store is that they be able to run a current version of firefox or chrome.
  
####What information will be collected?
*  Lot.line -- Auto generated, batch number and sequence number within batch, first screen has "start a new batch" button.
*  Set number -- Furniture often has a number of items all belonging to the same set. This field indicates that the item is part of the set by adopting the lot.line of the first set item encountered.
*  material -- free form text
*  dimension -- 100 character text field
*  location -- 40 character text
*  price -- number
*  color -- 40 char text
*  category/classification -- drop down from mysql table
*  Notes -- a 200 character optional description
*  datein -- when taken into store
*  datesold -- Sold items must remain visible on site for 2 weeks as enticement to act quickly

####How are the pictures associated with items?

  After the above information is entered into the database, price tags are printed at the store for a specific lot. Each price tag includes a barcode which uniquely identifies the item.
  
  Photogrphs, with unique file names, are synchronized with the information already entered into the database by, in every case, first making a photograph of the barcode. The photographs are sequentially uploaded to an appliction which uses the barcode to link each of the subsequent photos with the item that has been identified by the barcode.
  
####What provision for editing, reordeering, deleting, must be made for photos that are uploaded to the barcode recognition service?

  The photos are preprocessed in google picasa. Watermarks, cropping, enhancing can be done at that point. Picasa does not facilitate changing the filename (and therefore the order of the pictures related to a given item).
  
  Therefore there must be a mechanism for reviewing, reordering, perhaps deleting pictures after they are uploaded to the barcode recognition system.

####How will information about items for sale be presented to the customers' device?
* The device will have branding and direct access buttoms at the top and bottom of the screen, and an array of pictures in the middle region. Swiping vertically will scroll through available items, and horizontally will expose additional images related to a specific item.
* Items will, in general, be presented in the order they arrived in the store, with the most recent, first. 
* The search function will accept a large number of potential search words, which all get resolved to major categories (mapping is yet to be determined) and are returned in "most recent" first order.

####What resources are currently in place that might be helpful as models, or code snippets, to aid development of this project?

* This RFQ specifies a replacement for a current system, which in some ways is adequate. Information is currently collected via filemaker running locally, transfered to mysql via Microsoft Access, merged with pictures via php, and displayed in desktop thumbnail array via massivly transferred mysql db and image file sync to the ISP. See documentation for the current system at http://etgstores.com/furniture/database/furnitureintro.php.

* The current thinking is that the whole filemaker application can be replaced by a data colection screen, and a find/review lot screen running in the cloud, and contributing data directly to the mysql database.

* The barcode image recognition, uploading, reviewing, editing is currently implemented in php/mysql, and may be appropriate for reuse, by moving that code directly to the cloud machine.
    
* The display of an array of images, with thumbnails branching to detailed item information, is not appropriate for hand held devices, and needs to be replaced. (see http://etgstores.com/furniture/database/thumbnails.php)

####What do the new data entry screens require?
* Button to assign the next available lot number.
* Single lot.line data entry screen with each field set to maximum 
* A review lot screen with each item on its own line, with fields truncated if necessary, to fit 1280 pixel screen width. Each line must have a delete item button. A search field will bring up a lot review screen for previously entered lots.
