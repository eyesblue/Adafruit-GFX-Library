The library is fork from https://github.com/adafruit/Adafruit-GFX-Library
My github library: https://github.com/eyesblue/Adafruit-GFX-Library


The performance result compare with TFT_eSPI like this

	                    Adafruit GFX	TFT_eSPI	Winner
Screen fill	                147461	 2930664	Adafruit GFX
Text                      	171875	  165039	TFT_eSPI
Lines	                     1378906	  784179	TFT_eSPI
Horiz/Vert Lines	           20508	  238281	Adafruit GFX
Rectangles (outline)	       23438	  200195	Adafruit GFX
Rectangles (filled)	        405276	 8009767	Adafruit GFX
Circles (filled)	          263672	  666016	Adafruit GFX
Circles (outline)	          625000	  283203	TFT_eSPI
Triangles (outline)	        404297	  259765	TFT_eSPI
Triangles (filled)	        364258	 2613278	Adafruit GFX
Rounded rects (outline)	    257813	  276367	Adafruit GFX
Rounded rects (filled)	    503906	 8007812	Adafruit GFX


I got a conclusion from the result is Adafruit GFX bettre then the TFT_eSPI,
th TFT_eSPI is bad performance while fill color to a shape, I was move the 
drawLine and Circles (outline) code from TFT_eSPI to Adafruit GFX, the
result become

	                    Adafruit GFX	TFT_Espi	Winner
Screen fill	            147461     	 2930664	Adafruit GFX
Text    	              171875        165039	TFT_Espi
Lines	                  791015	      784179	TFT_Espi
Horiz/Vert Lines	       20508	      238281	Adafruit GFX
Rectangles (outline)	   23438	      200195	Adafruit GFX
Rectangles (filled)   	401372	     8009767	Adafruit GFX
Circles (filled)	      263672	      666016	Adafruit GFX
Circles (outline)	      326172	      283203	TFT_Espi
Triangles (outline)	    239258	      259765	TFT_Espi
Triangles (filled)	    365232	     2613278	Adafruit GFX
Rounded rects (outline)	256836	      276367	Adafruit GFX
Rounded rects (filled)	503906	     8007812	Adafruit GFX


The speed are improve.
