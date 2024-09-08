# MEDITERRANIAN INVESTIGATION

## Introduction

Mediterranean Investigation was a 24-hour OSINT-based challenge with a difficulty rated as medium and a total of 300 points. The task was to gather personal information about a target using open-source techniques.

The task was to investigate the name "anonymous57harper", and find the following informations:

- The user's real first name.
- The user's family name.
- The user's dog's name.
- The user's favourite anime.
- The user's university.
- The user's email.
- The user's job position.
- The user's favorite food.
- The user's favourite woman's name.

Once these information was gathered, we would need to put them together and fulfill the flag format of:

- `FSIIECTF{firstname_familyname_dogname_favouriteanime_university-name_favoritefood_jobposition_email_favouritewomansname}`

In the case of spaces in the word, we had to replace it with "-", and the spaces between words must be replaced by an underscore.

## Step 1: Username Search

With the given username Fanonymous57harper, the first instinct was to check whether this username was associated with any online profiles or social media accounts with the [What's My Name tool](https://whatsmyname.app/). After the search, the results were a github account with the name "anonymous57harper". Within said account, there was a GitHub repository called PetMealPlanner. The repo had a few files, including mainstart.go.

<div align="center">

![PetMealPlanner](images/PetMealPlanner.png)

</div>

Within said file, the code showed several important information that such as the user's dog name, his email and his job position.

<div align="center">

![Mainstart](images/mainstart.png)

<font color="red"> Email: hackcorp_pentester@gmail.com </font>, <font color="green"> Dog name: Rocky </font>, <font color="Red"> Job position: Pentester </font>

</div>

In the same image, the orange box highlighted the fact that the user attempted to not leak their name. This is also seen in the git commit history and if we backtrack it, we can see the latest changes which conveniently titled "avoid name leaking", contained the real name of the user.

<div align="center">

![Realname](images/name.png)
First name : Antoine, Family name : Fermier

</div>

## Step 2: Social Media Search
