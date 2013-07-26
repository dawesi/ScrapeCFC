ScrapeCFC
=========

A CFC that scrapes information from a given URL.

The use of ScrapeCFC requires Adobe ColdFusion 9+ or Railo 4. I have only test this on Railo so far, but believe it to work fine on ACF.

This script makes use of a Java class loader and a Java library known as jSoup. Combining these tools, we are able to extract information from a URL relatively easily.

There is only one public function <code>getData()</code> which can return either a ColdFusion structure, or JSON, when providing a URL and the output argument.

The following code assumes that your files are placed in a folder called lib, in your web root.

<pre>
&lt;cfparam name="url.url" type="string" default="" /&gt;
&lt;cfset scrape = new lib.scrape() /&gt;
&lt;cfdump var="#scrape.getData(url.url, "json")#" /&gt;
</pre>

This CFC returns Meta, Open Graph and Image information. Think of it more as a tool to scrape a summary of a web page, rather than the entire web page itself. 

The aim of this project was to acheive a similar scraping tool to that of Facebook; users sharing links on their timeline.
