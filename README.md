The library is fork from https://github.com/adafruit/Adafruit-GFX-Library

My github library: https://github.com/eyesblue/Adafruit-GFX-Library


The performance result compare with TFT_eSPI like this

|performance|		          Adafruit GFX|	TFT_eSPI|
|-----------|-------------------------|---------|
|Screen fill|                   147461|  2930664|
|Text|                          171875|   165039|
|Lines|			               **1378906**|**784179**|
|Horiz/Vert Lines|	             20508|	  238281|
|Rectangles (outline)|		       23438|	  200195|
|Rectangles (filled)|		        405276|	 8009767|
|Circles (filled)|		          263672|	  666016|
|Circles (outline)|		      **625000**|**283203**|
|Triangles (outline)|	          404297|	  259765|
|Triangles (filled)|	          364258|	 2613278|
|Rounded rects (outline)|	      257813|	  276367|
|Rounded rects (filled)|		    503906|	 8007812|



I got a conclusion from the result was Adafruit GFX bettre then the TFT_eSPI,
th TFT_eSPI is bad performance while fill color to a shape, I was move the 
drawLine and Circles (outline) code from TFT_eSPI to Adafruit GFX, the
result become



|performance|		          Adafruit GFX|	TFT_eSPI|
|-----------|-------------------------|---------|
|Screen fill|             			147461|	 2930664|
|Text|    			                171875|	  165039|
|Lines|				              **791015**|**784179**|
|Horiz/Vert Lines|		           20508|	  238281|
|Rectangles (outline)|		       23438|	  200195|
|Rectangles (filled)|		        401372|	 8009767|
|Circles (filled)|		          263672|	  666016|
|Circles (outline)|		      **326172**|**283203**|
|Triangles (outline)|		        239258|	  259765|
|Triangles (filled)|		        365232|	 2613278|
|Rounded rects (outline)|     	256836|	  276367|
|Rounded rects (filled)|		    503906|	 8007812|


The speed are improve.
