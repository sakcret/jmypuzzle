                         ____                          ___             
    __  /'\_/`\         /\  _`\                       /\_ \            
   /\_\/\      \  __  __\ \ \L\ \__  __  ____    ____ \//\ \      __   
   \/\ \ \ \__\ \/\ \/\ \\ \ ,__/\ \/\ \/\_ ,`\ /\_ ,`\ \ \ \   /'__`\ 
    \ \ \ \ \_/\ \ \ \_\ \\ \ \/\ \ \_\ \/_/  /_\/_/  /_ \_\ \_/\  __/ 
    _\ \ \ \_\\ \_\/`____ \\ \_\ \ \____/ /\____\ /\____\/\____\ \____\
   /\ \_\ \/_/ \/_/`/___/> \\/_/  \/___/  \/____/ \/____/\/____/\/____/
   \ \____/           /\___/                                           
    \/___/            \/__/                                            


//////////////////////////////////////////////////////////////////
/// (\_/)                                                      ///
/// (O.o) This is Bunny.                                       ///
/// (> <) Worship Bunny. There is only one, he is our god !    ///
//////////////////////////////////////////////////////////////////


http://www.enova-tech.net/lab/jMyPuzzle        

JMyPuzzle V-0.1

JMyPuzzle is an image carousel written in Javascript and based on the Jquery framework. To make it work you must have a copy of jquery in your website directories. 


### How do I install JMyPuzzle ?

Installing JMyPuzzle is very easy. Starting from the fact that you already know html and css, you just have to integrate to your web page the JMyPuzzle script, and to give it some custom parameters to make it work the way you want it (ajax functions, etc..). Using JMyPuzzle is very simple even though it is highly customizable. JMyPuzzle will take care of transforming a list of word or images into a dynamic puzzle.

Your html code should look like the one below :

   1. <div class="JMyPuzzle">  
   2.     <p id="trials"></p>
   3.     <ul>  
   4.         <li>or not</li>  
   5.         <li>be</li>  
   6.         <li>to</li>  
   7.         <li>question !</li>  
   8.         <li>To</li>  
   9.         <li>be,</li>  
  10.     </ul>  
  11.     <input type="button" class="button" id="reset" value="reset" />
  12.	  <input type="button" class="button" id="check" value="check" />
  13. </div>  


If you put image instead of words, please note that the size must be given. This is to avoid display bugs.

Once you have a proper html code showing your list, you are just two step away.

First, it is necessary to link the page with JQuery, this is the library requested by JMyPuzzle. After what we integrate the JMyPuzzlel script and its css presentation file :

   1. <link rel="stylesheet" type="text/css" href="JMyPuzzle.css" />  
   2. <script type="text/javascript" src="jquery.js"></script>  
   3. <!-- Some other scripts (jquery extensions) are also necessary to make it work. Have a look at ui.mouse, ui.draggable, and jquery.dimensions -->
   3. <script type="text/javascript" src="JMyPuzzle.js"></script>  

In this state, the carousel is ready to work. The only missing step is to pass the custom parameters that you wish for your custom carousel. In the example below, we set a carousel with a 100% width and scrolling image by image :

   1. $(function() {  
   2.     $(".JMyPuzzle").jMyPuzzle({  
   3.         fnOnCheck: function(jSonResults){ alert("Bravo !\nYour success rate : " + jSonResults.success_rate + "%") } 
   5.     });  
   6. });  


### What are the available configuration parameters ?

jMyCarousel has a lot of different configuration options :

   answer:"7,2,1,3,8,5,6,4",			// right answer's order
        
   maxTrials:3,							// maximum number of trials, 0 for unlimited
   classOnValid:'valid',				// class to apply to the element when valid
   classOnNotValid:'notValid',			// class to apply to the element when not valid
   classOnMiValid:'miValid',			// class to apply to the element when mi valid
        			
   fnOnCheck:null,						// To call its custom callback function at the end of the check. The function will be provided with the results variables of the exercise.
        								// example : function(jSonResults){ alert("Your success rate : " + jSonResults.success_rate + "%") }
        									
   ajaxResultUrl:'',					// Ajax url where to send the results. The results will be sent by post with the following variables :
        									// nb_words : The total number of words
        									// nb_valid : The number of valid elements (where the user is right)
        									// nb_not_valid : The number of non valid elements (where the user is not right)
        									// nb_mi_valid : The number of mi valid elements (at least 3 consecutive right elements, but not at the right place)
        									// success_rate : The success rate for the trial
        									// trial_nb : The trial number
        									// max_trials : The maximum number of trials allowed 
        									// answer : The answer given by the user
        										
  fnOnAjax:null,						// custom function to call at the end of the ajax treatment. enables to get the data sent back from the server : example function(data){ alert(data); }
        


You can have fun playing around with the different options.


### Is it possible to put something else that text or images in the puzzle ?

Yes if you wish so.. Feel free to let us know wether it works properly ! 
   

