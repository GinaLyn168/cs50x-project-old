# Bringing my character to life!
## Video Demo: https://youtu.be/aKwcZmtqmK0
### Background
Before I got the idea for my project, there was this web application called character.ai that you’ve probably heard about. The website is still around; it’s just fallen off due to controversies about its updates. When I first heard about it, I found it to be extremely fascinating; I’ve always liked art and writing in general, and I’ve been creating my own little fictional characters since I was young. So I tried out the website and eventually tried to make my own character on there based on one of the old characters I’ve created as a kid. However, even though I had fun doing so, I found that it was actually quite hard to get my character’s personality exactly right. As the website’s popularity gradually faded, I eventually gave up trying to make a bot of my character.
Then, a couple months ago, I started working on a project with a small team of people who utilized ChatGPT’s API to create a web app that helps with reading comprehension and analysis. That was when I first properly worked with an AI’s API and learned about prompt engineering, and I got the idea to make a character bot on my own by using an external AI language model. And that’s exactly what I did.
### Project description
Meet Shadow Girl! She’s one of the oldest original characters I’ve made and held onto over the years. I used Google’s Gemini API for her language model; the really long text section of the code is the system prompt, and it includes all of her character definition and information. I also collected old external documents about her personality and hobbies and inserted them into the prompt. The user’s input is attached toward the end of the system prompt, followed by a short conversation history to prevent the AI from forgetting their past messages immediately. The prompt also includes a request for the AI to return what it thinks is the emotion of the responses it generated, in a specific format that follows the original response. I then split off the emotion from the message and matched them with the emoji GIFs I animated to provide a visual for the response and make it more lively.
For the actual user interface, I originally chose to use PyQt5 because it can create a neat little pop-up window that’s perfect for my vision for this project. Since I wanted it to focus on the visual and response, I went for a minimalistic approach and didn’t really decorate much; the entire application is a small window consisting of a text box, an area for the text response, and the emotion GIF. However, when I uploaded it to CS50’s codepeace, I was disappointed to see that it refused to render my application, no matter what I changed. So, I modified my UI to be a web application by using Flask. I matched the background of the web page to be the same as the GIF’s background, as I based it off of the original color of the PyQT display window; the rest of the page follows the same minimalist design of the original app, with there being just a user input section, a response section, and an image section.
### Files description
**app.py:** The “brain” of the entire application; most of the code is located there. It handles the API and the prompting of, generating in-character responses and their corresponding emotions; it also stores the user’s input and the bot’s responses, but I’ve cut the conversation history short in order to not take up too many tokens. It handles matching the emotions to their respective GIFs and posting them to a web page using Flask as well.<br><br>
**Backstory.txt, c.ai_records.txt, CharacterInfo.txt, convo_examples.txt:** Text files of external character information that I’ve collected; they detail her personality, likes, fears, hobbies, and her style of conversation. They are then fed into the main prompt in app.py to define her character better.<br><br>
**README.md**: You’re here right now!<br><br>
**requirements.txt**: Includes external installations that are required to run this program.<br>
#### Templates folder
**index.html:** The actual web page display. app.py sends the generated response and emotion it gets to here, where it gets rendered into proper text and image. There’s also a text box the user can interact with to input their questions.<br>
#### Static folder
**angry.gif, happy.gif, neutral.gif, sad.gif, surprised.gif, very sad.gif:** Those are the emotion GIFs I animated! They are mapped to the emotion of each response to provide a visual for the character, making the interactions more authentic than if it were just text.<br><br>
**icon.ico:** Picture of Shadow Girl’s face as the website icon. Shows up on the tab.<br><br>
**Jojoba.otf:** The external font I used for the web page.<br><br>
**styles.css:** Decorates the page. I mostly used it to style the button, set the background color, and change the font of the page.<br>
### Setup instructions
Navigate to the project folder. Once there, run these commands in the terminal:<br>
```
pip install google.generativeai
pip install flask
pip install python.env
pip install python.dotenv
```
Afterwards, just run python `app.py` or `flask run` to deploy the web page!

### User instructions
The page design is fairly simple, as mentioned previously: to talk to my character, simply type something in the textbox and press “submit”! She’ll get right back to you :)

#### Have fun!
