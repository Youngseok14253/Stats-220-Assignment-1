
## “STATS 220 Semester One 2022”

# Github Repository Information

*https://github.com/Youngseok14253/Stats-220-Assignment-1*

# Animated GIF Creation

My meme was based on the reaction guys panel meme - this has to be one of my favourite meme templates, because of the way the atmosphere of the photo is so different in the two images. I have replaced the guys with **cats**, because who doesn't like cats??

![](https://pbs.twimg.com/media/E9cGC4YXMAAz7k_.jpg)

```{r gif}

library(magick)

happy_cat = image_read("https://i.pinimg.com/474x/bf/f5/d0/bff5d074d399bdfec6071e9168398406--so-funny-funny-pics.jpg") %>%
  image_scale(300)

angry_cat = image_read("https://steamuserimages-a.akamaihd.net/ugc/974352614523876225/E51FD04F339BDFAA0AC2E5BB47FF6DFCD1EB8200/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false") %>%
  image_scale(300)


top_text = image_blank(width = 300, 
                        height = 300, 
                        color = "#000000") %>%
  image_annotate(text = "Find a perfect IDE",
                 color = "#FFFFFF",
                 size = 40,
                 font = "Impact",
                 gravity = "center")


bottom_text = image_blank(width = 300, 
                        height = 300, 
                        color = "#FFFFFF") %>%
  image_annotate(text = "No Night Mode",
                 color = "#000000",
                 size = 50,
                 font = "Impact",
                 gravity = "center")

top_vector = c(happy_cat, top_text)
bot_vector = c(angry_cat, bottom_text)
top_row = image_append(top_vector)
bot_row = image_append(bot_vector)

meme_format = c(top_row, bot_row)

meme = image_append(meme_format, stack = TRUE) %>%
  image_scale(500)

image_write(meme, "my_meme.png")
```
