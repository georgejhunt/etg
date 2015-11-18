#Description of the desired system

####A. Purpose:

to collect, and present to customers, detailed information and pictures of furniture that is available for sale at ETG Furniture Store at 17 Brook in Staten Island.

####B. What computer hardware will be used for the application?

  The application will run on a computer in the cloud. The only requirement for local computers at ETG Furniture Store is that they be able to run a current version of firefox or chrome.
  
####C. What information will be collected?

1.  Lot.line -- Auto generated, batch number and sequence number within batch, first screen has "start a new batch" button.
2.  Set number -- Furniture often has a number of items all belonging to the same set. This field indicates that the item is part of the set by adopting the lot.line of the first set item encountered.
3.   material -- free form text
3.   dimension -- 100 character text field
1.   location -- 40 character text
1.   price -- number
1.  color -- 40 char text
1.  category/classification -- drop down from mysql table
1.  Notes -- a 200 character optional description
1.  datein -- when taken into store
1.  datesold -- Sold items must remain visible on site for 2 weeks as enticement to act quickly

####D. How are the pictures associated with items?
  1. After the above information is entered into the database, price tags are printed at the store for a specific lot. Each price tag includes a barcode which uniquely identifies the item.
  2. Photogrphs, with unique file names, are synchronized with the information already entered into the database by, in every case, first making a photograph of the barcode. The photographs are sequentially uploaded to an appliction which uses the barcode to link each of the subsequent photos with the item that has been identified by the barcode.
  
####E. What provision for editing, reordeering, deleting, must be made for photos that are uploaded to the barcode recognition service?

  The photos are preprocessed in google picasa. Watermarks, cropping, enhancing can be done at that point. Picasa does not facilitate changing the filename (and therefore the order of the pictures related to a given item).
  
  Therefore there must be a mechanism for reviewing, reordering, perhaps deleting pictures after they are uploaded to the barcode recognition system.

####F. How will information about items for sale be presented to the customers' device?
* The device will have branding and direct access buttoms at the top and bottom of the screen, and an array of pictures in the middle region. Swiping vertically will scroll through available items, and horizontally will expose additional images related to a specific item.
* Items will, in general, be presented in the order they arrived in the store, with the most recent, first. 
* The search function will accept a large number of potential search words, which all get resolved to major categories (mapping is yet to be determined) and are returned in "most recent" first order.

####G. What resources are currently in place that might be helpful as models, or code snippets, to aid development of this project?

* This RFQ specifies a replacement for a current system, which in some ways is adequate. Information is currently collected via filemaker running locally, transfered to mysql via Microsoft Access, merged with pictures via php, and displayed in desktop thumbnail array via massivly transferred mysql db and image file sync to the ISP. See documentation for the current system at http://etgstores.com/furniture/database/furnitureintro.php.

* The current thinking is that the whole filemaker application can be replaced by a data colection screen, and a find/review lot screen running in the cloud, and contributing data directly to the mysql database.

* The barcode image recognition, uploading, reviewing, editing is currently implemented in php/mysql, and may be appropriate for reuse, by moving that code directly to the cloud machine.
    
* The display of an array of images, with thumbnails branching to detailed item information, is not appropriate for hand held devices, and needs to be replaced. (see http://etgstores.com/furniture/database/thumbnails.php)

####H. What data entry screens are required?
1. An intake screen with a button to assign the next available lot number, item name drop down field, and check boxes for the required tasks for that item (cleaning, repair, pricing, tagging, moving to floor).
2. A details screen for each item which collects the size, features, condition, materials, location, price information ( one item per page with all available fields set to maximum size).
3. A review lot screen with each item on its own line, with fields truncated if necessary, to fit 1280 pixel screen width. Each line must have a delete item button. A search field will bring up a lot review screen for previously entered lots.
4. The lot review screen may double as the print label selector.
5. It might also be used to break sets (remove the set id, and assign a separate price to a single item).
6. A data collection form which accepts a barcode (or lot.line), and optionally a new location, for generation of move lists, receipts for movie companies, and at cash register checkout. The logic of this form might also be useful to an online customer to generate a list of items in preparation for a visit to the store.

####I. What output forms and program outputs are needed?
1. Print a tag for a single item, with barcode, item name, price, description, size, material
2. Print a set of tags for a set, with the same barcode for all, a price for the set, and a list of other items that are in that set.
3. Print a list of items (input via H.6 above) with old location, new location (for generating a move list), item name, lot.line, price (with optional output to a file so that the list can be emailed to movie companies as a receipt). This report might also be used at the cash register as part of the regular check out procedure for customers. It might also optionally fill in the datesold field in the database.

####J. What security requirements are associated with running the database in the Cloud?
* Authentication of clients in the store should require Secure Socked Layer (https) 

####K. What additional Tasks are part of this request?
* The new system should run in parallel with the current system for at least one month.
* Training of the staff in using the new system should be included in the roll out.
* Migration of the current inventory to the new system should occur before the month of trial run.
