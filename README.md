# Define the required modules
import string
import random

# Define the questions, options, and answers
questions = ["What is the capital city of France?",
 "Who invented the telephone?", 
"What is the largest country in the world?", 
"What is the highest mountain in the world?", 
"What is the smallest planet in our solar system?", 
"What is the largest planet in our solar system?", 
"What is the tallest animal in the world?", 
"What is the largest animal in the world?", 
"What is the most common element in the earth's atmosphere?", 
"What is the name of the currency used in Japan?", 
"What is the smallest continent in the world?", 
"What is the largest ocean in the world?", 
"Who painted the Mona Lisa?", 
"What is the name of the longest river in the world?", 
"What is the name of the world's largest desert?", 
"Who is the CEO of Microsoft?"
"In 1768, Captain James Cook set out to explore which ocean?",
"Which one of the following river flows between Vindhyan and Satpura ranges?",
"The Central Rice Research Station is situated in?",
"Who among the following wrote Sanskrit grammar?"]
options = [["A. Paris", "B. Berlin", "C. London"], 
["A. Alexander Graham Bell", "B. Thomas Edison", "C. Albert Einstein"], 
["A. Russia", "B. Canada", "C. China"], 
["A. Mount Everest", "B. K2", "C. Mount Kilimanjaro"], 
["A. Mercury", "B. Venus", "C. Mars"],
 ["A. Jupiter", "B. Saturn", "C. Uranus"],
 ["A. Giraffe", "B. Elephant", "C. Lion"],
 ["A. Blue whale", "B. African elephant", "C. Colossal squid"],
 ["A. Oxygen", "B. Nitrogen", "C. Carbon dioxide"], 
["A. Yen", "B. Won", "C. Yuan"], 
["A. Australia", "B. Europe", "C. Antarctica"], 
["A. Pacific Ocean", "B. Indian Ocean", "C. Atlantic Ocean"], 
["A. Leonardo da Vinci", "B. Vincent van Gogh", "C. Pablo Picasso"], 
["A. Amazon", "B. Nile", "C. Yangtze"],
 ["A. Sahara", "B. Arabian", "C. Gobi"],
["A.Steve Jobs", "B.Bill Gates", "C.Satya Nadella"],
 ["A. Pacific Ocean", "B. Atlantic Ocean", "C. Indian Ocean"],
 ["A. Mahanadi" "B. Son", "C. Narmada"],
 ["A.Bangalore", "B. Cuttack", "C.Quilon"],
 ["A.Kalidasa", "B.Panini", "C. Aryabhatt"]]
answers = ["A", "A", "A", "A", "A", "A", "A", "B", "B", "A",
           "C", "A", "A", "B", "A", "C", "A", "c", "B", "B"]
# Get the number of teams and their names
num_teams = int(input("How many teams are participating? "))
team_names = []
for i in range(num_teams):
    name = input("Enter the name of team {}: ".format(i+1))
    team_names.append(name)

# Create a dictionary to store each team's score
scores = {}
for name in team_names:
    scores[name] = 0

# Shuffle the questions and options
questions_options = list(zip(questions, options, answers))
random.shuffle(questions_options)

# Ask each team each question and keep track of their scores
for i, (question, options, answer) in enumerate(questions_options):
    name = team_names[i % num_teams]
    print("\n{}'s turn to answer:".format(name))
    print("\nQuestion: {}".format(question))
    for option in options:
        print(option)
    user_answer = input("Your answer (A/B/C): ")
    if user_answer.lower() == answer.lower():
        scores[name] += 1

# Display each team's score
print("\nFinal Scores:")
for name, score in scores.items():
    print("{}: {}".format(name, score)
