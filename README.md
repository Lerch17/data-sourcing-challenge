my read me
    Deal with APIs was very challenging for me. I stumbled a lot at the beginning because i had not set up my query URL correctly and i kept getting empty lists as a respopnse. i tested my API keys and returned a string confirming that my API keys are being read. Once I got this figured out i was able to retireve the reviews and begin manupulating them. 
    we then print out the first 5 results in JSON format and see the data from 5 different movies. I then converted the data into a dataframe where it is put into a format that is easy to read. I then extracted the "headline.main" column and renamed it while using the lambda function provided. 
    ** I stumbled with this because the example didnt have the function in parentheses**
    I then created an empty list to store the results of our imdb search. I worked on this part with a classmate, and we found that we could make things easier to code by making some definitions (get_items and get_movie_details) at the beginning. This helped us extract what we needed and append it to the list individually from the rest of the data. we then manipulate the data we get the same way we did earlier by converting it to JSON form, and only including the first 5 results in the list.
    I then converted this data into a dataframe and merged it with the first result on the titles.
    we then edit our columns and remove characters given to us in the hw. at the end we drop the "byline.person" column, delete duplicate rows and reset the index. finally we upload to CSV.

    KEY TAKEAWAYS
    - make sure your query URL is entered correctly. anytime your list shows no values, this is likely the cause.
    -once you successfully pull the information from the API formating and converting to DataFrame is easy and just a line of code typically.
    -I am much more comfortable with manipulating the information once it is id a dataframe than i am pulling the API infomation

    COLABERATION 
    I worked with a classmate, Issac, on Part 2: Access The Movie Database API and with the help of microsoft co-pilot we created some two definitions at the beginning to make coding easier as we went on. the code is :
    
    def get_items(list_to_save, list_to_loop, name):
    for item in list_to_loop:
        list_to_save.append(item[name])

def get_movie_details(movie_id, tmdb_api_key):
    query_url = "https://api.themoviedb.org/3/movie/"
    url = f"{query_url}{movie_id}?api_key={tmdb_api_key}"
    movie_response = requests.get(url).json()
    return movie_response