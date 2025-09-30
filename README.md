# %30 first midterm, %30 second midterm, %40 final notes defined. Take and create file them average.

#calculate the notes and to add them to files...
def calculate_notes(line):
    lines = line[:-1]
    lines = lines.split(',')
    name = lines[0]
    midterm_1 = float(lines[1])
    midterm_2 = float(lines[2])
    final = float(lines[3])
    average_notes = midterm_1 * 3/10 + midterm_2 * 3/10 + final * 4/10

    # adding process with if-elif-else commands
    if average_notes >= 90:
        letter = 'AA'
        with open('succesful.txt','a',encoding='utf-8') as file_3:
           file_3.write(name + '---------->' + str(average_notes) + '---------->' + letter + '\n')
    elif average_notes >= 85 and average_notes <= 90:
        letter = 'BA'
        with open('succesful.txt','a',encoding='utf-8') as file_3:
           file_3.write(name + '---------->' + str(average_notes) + '---------->' + letter + '\n')
    elif average_notes >= 75 and average_notes <= 85:
        letter = 'BB'
        with open('succesful.txt','a',encoding='utf-8') as file_3:
           file_3.write(name + '---------->' + str(average_notes) + '---------->' + letter + '\n')
    elif average_notes >= 65 and average_notes <= 75:
        letter = 'CB'
        with open('succesful.txt','a',encoding='utf-8') as file_3:
           file_3.write(name + '---------->' + str(average_notes) + '---------->' + letter + '\n')
    elif average_notes >= 55 and average_notes <= 65:
        letter = 'CC'
        with open('succesful.txt','a',encoding='utf-8') as file_3:
           file_3.write(name + '---------->' + str(average_notes) + '---------->' + letter + '\n')
    elif average_notes >= 45 and average_notes <= 55:
        letter = 'DC'
        with open('succesful.txt','a',encoding='utf-8') as file_3:
           file_3.write(name + '---------->' + str(average_notes) + '---------->' + letter + '\n')
    else:
        letter = 'FF'
        with open('not_succesful.txt','a',encoding='utf-8') as file_2:
            file_2.write(name + '---------->' + str(average_notes) + '---------->' + letter + '\n')

    return name + '---------->' + str(average_notes) + '---------->' + letter

# create a list that for reading lines...
final_form = []

# open main txt file and transfer to calculate_notes function...
with open('class_notes_information.txt','r',encoding='utf-8') as file:
    for i in file:
        final_form.append(calculate_notes(i))

# print command for see...
for x in final_form:
    print(x)
