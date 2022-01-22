import string
rude_words = ["crap", "darn", "heck", "jerk", "idiot", "butt", "devil"]
new_context = ""

def bleeper(word):
    pos = 0 
    for character in word:
        if character not in string.punctuation:
            character = "*"
        word = word.replace(word[pos], character) 
        pos += 1
    return word

def check_line(line):
    print(new_context)
    rude_count = 0
    words = line.split(" ")
    for word in words:
        stripped_word = word.strip(string.punctuation).lower()
        if stripped_word in rude_words:
            word = bleeper(word)
            rude_count += 1
            print(f"Found rude word: {word}")
        new_context = new_context + word + " "
    new_context = new_context + "\n"
        
    return rude_count

def check_file(filename):
    with open(filename) as myfile:
        rude_count = 0
        for line in myfile:
            rude_count += check_line(line)

    if rude_count == 0:
        print("Congratulations, your file has no rude words.")
        print("At least, no rude words I know.")

if __name__ == '__main__':
    check_file("my_other_story.txt")
    print(new_context)
