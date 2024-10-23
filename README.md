# Recommendation System For Book Lovers
Today I’m presenting a recommendation system that predicts wich books certain users are likely to enjoy, based on their previous interactions, such as book reviews and ratings. Because, as a wise old lady always says, reading is fundamental.

This was [my final project](https://github.com/OlyZink/Recommendation-System-For-Book-Lovers/blob/main/Recommendation%20System%20for%20Books.pptx) for the AllWomen AI Applied Bootcamp, which included AWS technologies. 

This project contains two notebooks: one for [data preprocessing and cleaning](https://github.com/OlyZink/Recommendation-System-For-Book-Lovers/blob/main/Cleaning%20and%20preprocessing%20dataset.ipynb), that includes some NLP techniques, and another notebook for [model training and the expected output](https://github.com/OlyZink/Recommendation-System-For-Book-Lovers/blob/main/Predicting%20and%20recommending%20books.ipynb). I wanted to base this Project on reliable data, such as a Goodreads data, but the Goodreads API was shut down in 2020, so I started by navigating through Kaggle and Hugging Face, looking for datasets. Kudos to Abhishek Thakur for his Goodreads autotrain notebook, which contains [the dataset used for this project](https://www.kaggle.com/code/abhishek/goodreads-autotrain/notebook).

**Dataset and Preprocessing** (Cleaning and preprocessing dataset.ipynb)

I began exploring, cleaning and preprocessing the dataset, removing missing or irrelevant data. I even applied some NLP techniques that weren't really necessary for the recommendation system, since the Surprise Library doesn't use them, but  really useful to have on hand for preprocessing text. Just a heads-up, the dataset is quite large. I had to use AWS Cloud to handle it properly, as I wasn't able to work with it on my laptop. I used Pandas to structure data in a format that the Surprise Library can work with for collaborative filtering.

**Building the Model** (Predicting and recommending books.ipynb)

I used a K-Nearest Neighbors algorithm, a collaborative filtering technique, which is a fancy way of saying: 'Find people who like similar books'. To train the model, we took our dataset of book ratings and split it in two—one part for the model to learn from and the other part to test how well it makes predictions. Right now, the model is built with five preset profiles: Adam, Lucrecia, Maria, Peter, and Andrea. These are the only options available, meaning the system is limited to recommending books for these specific users.

**User interaction**

To make it easy to use, I integrated something called Gradio. Its a simple web interface where users can just type in their name and the number of book recommendations they want. Just enter the info, and the system does the rest. And here’s another cool part: the dataset we use for the model (the one from Surprise) doesn’t contain book titles, so, to give the recommendations some personality, we had to get a bit creative. For each book the system recommends, it goes online and scrapes Goodreads to grab the actual book title and author name using BeautifulSoup and requests. This way, when you get a recommendation, you’re not just seeing a book ID, but the actual details, making the experience feel more user-friendly.

**Next Steps**

One idea for the future of this model, is to let anyone enter their own Goodreads user ID, and based on that information, the model will make live predictions about which books they should read next, creating a more dynamic and personalized experience for each user.

If you want to know a little more, feel free to read [my final project presentation](https://github.com/OlyZink/Recommendation-System-For-Book-Lovers/blob/main/Final%20Project%20Description.docx), there is even [a PPT](https://github.com/OlyZink/Recommendation-System-For-Book-Lovers/blob/main/Recommendation%20System%20for%20Books.pptx) included!

This Project was challenging and fun to make. I want to give a huge thank you to the AllWomen community, my amazing teachers, my peers, and of course, to all of you for reading. I hope you all find your next favorite book! Thanks again, and happy reading!


![More Books!](https://media1.tenor.com/m/WyMXh9GqOF0AAAAC/bibliophile-dive-into-a-book.gif)

