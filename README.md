
                         ____                          ___
    __  /'\_/°\         /\  _'\                       /\_ \
   /\_\/\      \  __  __\ \ \L\ \__  __  ____    ____ \//\ \      __   
   \/\ \ \ \__\ \/\ \/\ \\ \ ,__/\ \/\ \/\_ ,'\ /\_ ,'\ \ \ \   /'__'\
    \ \ \ \ \_/\ \ \ \_\ \\ \ \/\ \ \_\ \/_/  /_\/_/  /_ \_\ \_/\  __/ 
    _\ \ \ \_\\ \_\/'____ \\ \_\ \ \____/ /\____\ /\____\/\____\ \____\
   /\ \_\ \/_/ \/_/'/___/> \\/_/  \/___/  \/____/ \/____/\/____/\/____/
   \ \____/           /\___/                                           
    \/___/            \/__/                                            


//////////////////////////////////////////////////////////////////
/// (\_/)                                                      ///
/// (O.o) This is Bunny.                                       ///
/// (> <) Worship Bunny. There is only one, he is our god !    ///
//////////////////////////////////////////////////////////////////


http://www.enova-tech.net/lab/jMyPuzzle        

JMyPuzzle V-0.2

JMyPuzzle is an word puzzle written in Javascript and based on the Jquery library. To make it work you must have a copy of jquery in your website directories, or use the jquery CDN.


### How do I install JMyPuzzle ?

Installing JMyPuzzle is very easy. Starting from the fact that you already know html and css, you just have to integrate to your web page the JMyPuzzle script, and to give it some custom parameters to make it work the way you want it (ajax functions, etc..). Using JMyPuzzle is very simple even though it is highly customizable. JMyPuzzle will take care of transforming a list of word or images into a dynamic puzzle.

Your html code should look like the one below :
```html
<div class="JMyPuzzle">
    <p id="trials"></p>
        <ul>
            <li>or not</li>
            <li>be</li>
            <li>to</li>
            <li>question !</li>
            <li>To</li>
            <li>be,</li>
    </ul>
    <input type="button" class="button" id="reset" value="reset" />
    <input type="button" class="button" id="check" value="check" />
</div>
```

If you put image instead of words, please note that the size must be given. This is to avoid display bugs.

Once you have a proper html code showing your list, you are just two step away.

First, it is necessary to include jquery and jqueru UI libraries in the page.
After what we integrate the JMyPuzzlel script and its css presentation file :
```html
<link rel="stylesheet" type="text/css" href="css/jmypuzzle.css" />
<script src="https://code.jquery.com/jquery-1.11.1.min.js"></script>
<script src="https://code.jquery.com/ui/1.11.1/jquery-ui.min.js"></script>
<script type="text/javascript" src="js/jmypuzzle.min.js"></script>
```

In this state, the puzzle is ready to work.

```javascript
$(function() {
    $(".JMyPuzzle").jMyPuzzle({
        fnOnCheck: function(jSonResults){ alert("Bravo !\nYour success rate : " + jSonResults.success_rate + "%") }
    });
});
```

### What are the available configuration parameters ?

jMyCarousel has a lot of different configuration options :

**answer:** "7,2,1,3,8,5,6,4",			// right answer's order
        
**maxTrials:** 3,							// maximum number of trials, 0 for unlimited
**classOnValid:** 'valid',				// class to apply to the element when valid
**classOnNotValid:** 'notValid',			// class to apply to the element when not valid
**classOnMiValid:** 'miValid',			// class to apply to the element when mi valid
        			
**fnOnCheck:** null,						// To call its custom callback function at the end of the check. The function will be provided with the results variables of the exercise.
        								// example : function(jSonResults){ alert("Your success rate : " + jSonResults.success_rate + "%") }
        									
**ajaxResultUrl:** '',					// Ajax url where to send the results. The results will be sent by post with the following variables :
        									// nb_words : The total number of words
        									// nb_valid : The number of valid elements (where the user is right)
        									// nb_not_valid : The number of non valid elements (where the user is not right)
        									// nb_mi_valid : The number of mi valid elements (at least 3 consecutive right elements, but not at the right place)
        									// success_rate : The success rate for the trial
        									// trial_nb : The trial number
        									// max_trials : The maximum number of trials allowed 
        									// answer : The answer given by the user
        										
**fnOnAjax:** null,						// custom function to call at the end of the ajax treatment. enables to get the data sent back from the server : example function(data){ alert(data); }
        


You can have fun playing around with the different options.


### Is it possible to put something else that text or images in the puzzle ?

Yes if you wish so.. Feel free to let us know wether it works properly ! 
   

