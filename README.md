Add-license-links-to-Library-Systems
====================================

Add license links to library systems (360Link, Voyager OPAC and Summon).

I. The license database:

1) Set up an internal database which have one table(I called it “provider” in the script) and it contains the following columns:

    the titles in the vendor systems(A), the titles in your current license database(B) if you already have one, and the urls(C) of the page which contains the license information.
    A: contains the titles in the vendors systems, for example: title in 360, title in Summon, title in Voyager (if they are different for one resource in the above three systems).
    B: If you already have a database which contains the license information, and the url for each title( in our case, we have a license database which is hosted by Scholars Portal - Queen’s Licenses), you just need to match the titles in A and B, and assign C to A. Then, you need to have B column, if you don’t have a current license database, you don’t need column B.
    (Please see the How to get urls from sites for the instruction)
    C: the url for the license page
    i. If you have an internal license DB which you need to match the licenses with. 	ii. If you don’t have an internal license DB, then you need to create one.
    
    Here is an example: table name in mySQL database: provider
    Please see ]this page for the instruction to get the urls and make this table
    title_360 	title_SP 	        URL_OUR
    ABI Inform 	ABI Inform 	      http://queens.scholarsportal.info/licenses/ABI_Inform
    Springer 	  Springer eBooks 	http://queens.scholarsportal.info/licenses/Springer_eBooks

2) Copy a javascript file from our site to yours and write down the url to that file. It’s copied from JQuery sites.  jquery-1.9.0.js (http://library.queensu.ca/devel/testing/360link/jquery-1.9.0.js)


II: Add the links to 360 Link search result pages:

    Edit the 360_get_name.js. You need to replace the url in this file with the file path on your site.
    Insert 360_get_names.js and the jquery-1.9.0.js to Serials Solutions’ Client Center>360 Link Admin
    Add the libraryLicenses.php file to your server and define the path in the 360_get_name.js on your site
    You can test and see how it looks the next day. (Give 24 hours before it works)
    If you can get the license links added in 360 Link, you can add it to Summon and Voyager, or any other systems if you can insert a link in their interface.

 
III: Add the links to ILS- Voyager record display page:
    Add the "Voyager License links" to your Voyager Web server: xsl/contentLayout/display/display.xsl file in the xsl:template name=”BMD3000″

