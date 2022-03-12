<!DOCTYPE html>

<!-- Fig. 9.6: RollDice.html -->
<!-- Rolling 12 dice and displaying frequencies. -->
<html>
 <head>
    <meta charset = "utf-8"> 
    <title>Die Rolling Frequencies</title> 
    <h1>"NAME=ZULQARNAIN ALI"</h1>
    <H1>"REGNO=451-FBAS/BSIT/F19"</H1>
    <style type = "text/css"> 
     img { margin-right: 10px;}

     table { width: 200px; 
            border-collapse: collapse;
            background-color: lightblue;}   
    table, td, th { border: 1px solid black; 
                    padding: 4px; 
                    margin-top: 20px;}
        th { text-align: left;
            color: white;
            background-color: darkblue;} 
</style> 
<script> 
    var frequency1 = 0;
    var frequency2 = 0;
    var frequency3 = 0;
    var frequency4 = 0;
    var frequency5 = 0;
    var frequency6 = 0;
    var totalDice = 0;

    // register button event handler
    function start() 
    {
        var button = document.getElementById( "rollButton" ); 
        button.addEventListener( "click", rollDice, false );
    } //end function start
     
    // roll the dice 
     function rollDice() 
    {
        var face; // face rolled 
        // loop to roll die 12 times
        for ( var i=1; i <=12; ++i ) 
        {
            face = Math.floor( 1 + Math.random() * 6 ); 
            tallyRolls( face );
            setImage( i, face ); // display appropriate die image 48
             ++totalDice; // increment total
        } //end die rolling loop
            updateFrequencyTable(); 
        } // end function rollDice 
         // increment appropriate frequency counter
            function tallyRolls( face ) 
        {
            switch ( face )
        {
            case 1:
            ++frequency1;
            break;
            case 2:
            ++frequency2;
            break;
            case 3:
            ++frequency3;
            break;
            case 4:
            ++frequency4;
            break;
            case 5:
            ++frequency5;
            break;
            case 6:
            ++frequency6;
            break;
        } //end switch function
        //end tallyrolls
        
        //set image source for die
        function setImage( dieNumber, face )
        {
            var dieImg = document.getElementById( "die" + dieNumber );
             dieImg.setAttribute( "src", "die" + face +".png" );
             dieImg.setAttribute( "alt", "die with " + face +" spot(s)" );
        } // end function setImage

        
        function updateFrequencyTable()
        {
            var tableDiv = document.getElementById( "frequencyTableDiv" );

        tableDiv.innerHTML = "<table>" +
            "<caption>Die Rolling Frequencies</caption>" + 
            "<thead><th>Face</th><th>Frequency</th>" + 
            "<th>Percent</th></thead>" + 
            "<tbody><tr><td>1</td><td>" + frequency1 + "</td><td>" + 
            formatPercent(frequency1 / totalDice) + "</td></tr>" + 
            "<tr><td>2</td><td>" + frequency2 + "</td><td>" +
            formatPercent(frequency2 / totalDice)+ "</td></tr>" +
            "<tr><td>3</td><td>" + frequency3 + "</td><td>" +
            formatPercent(frequency3 / totalDice) + "</td></tr>" +
            "<tr><td>4</td><td>" + frequency4 + "</td><td>" +
            formatPercent(frequency4 / totalDice) + "</td></tr>" +
            "<tr><td>5</td><td>" + frequency5 + "</td><td>" + 
            formatPercent(frequency5 / totalDice) + "</td></tr>" +
            "<tr><td>6</td><td>" + frequency6 + "</td><td>" +
            formatPercent(frequency6 / totalDice) + "</td></tr>" +
            "</tbody></table>";

        } // end function updateFrequencyTabl

    // format percentage 
    function formatPercent( value )
    {
        value *= 100; 
        return value.toFixed(2);
     } // end function formatPercen
     window.addEventListener( "load", start, false );
    </script> 
    </head>
    <body>
        <p><img id = "die1" src = "images.jpg" alt = "die 1 image">
            <img id = "die2" src = "2.png" alt = "die 2 image">
            <img id = "die3" src = "3.png" alt = "die 3 image">
            <img id = "die4" src = "4.png" alt = "die 4 image">
            <img id = "die5" src = "5.png" alt = "die 5 image"> 
            <img id = "die6" src = "6.png" alt = "die 6 image"></p> 
            <p><img id = "die7" src = "2.png" alt = "die 7 image"> 
            <img id = "die8" src = "3.png" alt = "die 8 image"> 
            <img id = "die9" src = "5.png" alt = "die 9 image"> 
            <img id = "die10" src = "4.png" alt = "die 10 image"> 
            <img id = "die11" src = "2.png" alt = "die 11 image"> 
            <img id = "die12" src = "1.png" alt = "die 12 image"></p> 
            <form action = "#"></form>
            <input id = "rollButton" type = "button" value = "Roll Dice"> 
            </form>            
            <div id = "frequencyTableDiv"></div>
            </body>
            </html>













































