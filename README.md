# Comic Assignment - *Missing Cat*

## Eunsu Choi, Maya Lee, Tina Zhang, Chinonyerem Ukaegbu

### **Description**

It has been 585 days since March 7th, 2020, the day of school closure at NYUAD. With all classes turning remote, many students reported that the campus residents heavily depend on the campus cats for their mental health and healing. Until there was a cat missing…
Where did the cat go?

This comic project leads the readers to narrowing down the exact place the cat went. Readers get to talk to a catmom, fellow campus cats, and looks around the map, and then the cat-napper calls the reader to tease them, but the cat-napper gets caught at the airport.

### **Implementation**

+ **Panel 1**
  
  The first panel sets an introduction to the whole comic. It introduces how a cat has gone missing and the whole journey is about finding it! Photoshop was used to crop the image of the wanted cat. After that, a black and white filter (done through grayscale) was used to deliver a serious mood.
  

+ **Panel 2**
  
  The second panel shows the cats and the cat mom being interviewed. This panel provides clues and hints as to where the missing cat might be which influences the decisions the reader makes in the next panel. The images were placed in a grid and the grid-template-areas properties was used to position the images. Then the speech bubbles were downloaded as PNGs with transparent backgrounds. And then, the opacity of the speech bubbles was set to 0 and would only be displayed when the reader hovers over the image.
  
  
+ **Panel 3**
  
  The first panel sets an introduction to the whole comic. It introduces how a cat has gone missing and the whole journey is about finding it! 

  Photoshop was used to crop the image of the wanted cat. After that, a black and white filter (done through grayscale) was used to deliver a serious mood.
  

+ **Panel 4**
  
  Photoshop was used to edit the image and illustrator to trace the image and buttons to allow for interactivity. The class name was called from the svg file to start the ringtone when hovered on the top, make colors darken when buttons are hovered, and to trigger sound when clicked on the green button. Then logic was applied to distort the audio and make it sound spooky.
  

+ **Panel 5**
  
  Photoshop was used to edit the image and illustrator to trace the image and buttons to allow for interactivity. The class name was called from the svg file to start the ringtone when hovered on the top, make colors darken when buttons are hovered, and to trigger sound when clicked on the green button. Then logic was applied to distort the audio and make it sound spooky.
  

+ **Panel 6**
  
  Finally!! This panel shows you who the criminal was. Speech balloons were used to make it seem like there were actual dialogues. The location was set by giving specific location through percentages.
  

+ **Ending Page**
  
  The ending page wraps up the comic by granting you a huge amount of money! A cute image with the message "Congratulations You Won!" and an image of a happy cat is displayed! The adventure is over but if the reader would like to play again, they can either click the 'Go Back to Home' button on the navigation bar which will take them to the index page, or click the 'Missing Cat' button which will take them to the first panel.


**Process**

There were a couple of datasets with the song lyrics separated by line number, but I needed the lyrics to be represented by one value per song entry, and then I came upon the data set accessible through this link:
[Taylor Swift Dataset](https://github.com/rochelleterman/FSUtext/blob/master/02_Dictionary/taylor_swift.csv)

</br>
I needed to count the number of characters per song lyric so I first had to download the CSV file, load it up in Excel, remove the forward slashes(/) that had been used to separate each line and then use an excel formula to calculate the number of characters in each song lyric entry.
</br>
I did not need the column for the artiste's name and because each album was released in a different year, I deleted the column for album name and opted to use the column for year of release as an identifier instead.

</br>
I then created four files, one for the year of release, one for the track number, one for the length of lyrics and the last for the title of the tracks and loaded them into Processing.

```js
String year[];
String track_n[];
String lyric_length[];
String track_title[];


void setup() {
  size(1600, 1000);
  background(105, 102, 103);

  //Load files into array
  
  year = loadStrings("year.csv");
  track_n = loadStrings("track_n.csv");
  lyric_length = loadStrings("lyric_length.csv");
  track_title = loadStrings("track_title.csv");
  ```

After I decided that I wanted the data to be represented as circles, I got to work on translating the data into what I had planned in Processing. The radius of the circle increased as the length of the lyrics increased, the songs that were from the same album had the same colour and the songs that had the same track number from various albums were on the same y-axis
I did this by playing around with some values until I was ultimately satisfied with what the code looked like

```js
for ( int i = 0; i < yearData.length; i++) {
    if (yearData[i]==2006) {   //2006
      fill(255, 236, 148);
      circle(random(200, 1400), track_nData[i]+50, lyric_lengthData[i]/20);
    }
    if (yearData[i]==2008) {   //2008
      fill(255, 174, 174);
      circle(random(200, 1400), track_nData[i]+50, lyric_lengthData[i]/20);
    }
    if (yearData[i]==2010) {   //2010
      fill(143, 96, 72);
      circle(random(200, 1400), track_nData[i]+50, lyric_lengthData[i]/20);
    }
    if (yearData[i]==2012) {   //2012
      fill(176, 229, 124);
      circle(random(200, 1400), track_nData[i]+50, lyric_lengthData[i]/20);
    }
    if (yearData[i]==2014) {   //2014
      fill(180, 216, 231);
      circle(random(200, 1400), track_nData[i]+50, lyric_lengthData[i]/20);
    }
    if (yearData[i]==2017) {   //2017
      fill(86, 186, 236);
      circle(random(200, 1400), track_nData[i]+50, lyric_lengthData[i]/20);
    }
    fill(255, 255, 255);
   
   ``` 
   
The final output looked like this:

![Final](images/Screenshot%20(195).png)

**Difficulties**

The major difficulty I faced was with reading data from a CSV file with multiple columns. I wanted to access the data in a column and not in a row but I couldn't find any function that could do that which was why I had to seperate the fields into different CSV files in the first place. 

**Interesting Things I Found**

I found out that there was a circle() function. I thought it was only ellipse() that was available. I could've used ellipse() of course but circle() was much more convenient.
Also, even though I didn't use it in this program, I learnt how to create or read data from tables in Processing.

**Possible Improvements**

I wanted to use a sort of mouseOver function so that anytime the mouse hovered over a circle, the name of the song would be displayed but I did not know how to. I believe I'd have to rewrite the program and include a class so that that would be implementable and it would really pull the design together. 

**Conclusion**

At first, I thought the assignment was going to be really boring because it seemed like dealing with datasets was just tedious and uninteresting. However, manipulating these data sets and being able to create visuals is actually reallyu cool and the possibilites are really endless when it comes to data manipulation and visualization.
