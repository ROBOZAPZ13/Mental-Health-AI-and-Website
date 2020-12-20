import speech_recognition as sr
import pyttsx3
import webbrowser
import time
import datetime
import smtplib
from pygame import mixer
import os
current_time = datetime.datetime.now()
r=sr.Recognizer()
nani = 0
print("\n'Baymax' AI:\nCreated by:\n Untitled")
def SpeakText(command):
    engine=pyttsx3.init()
    engine.say(command)
    engine.runAndWait()

def password():
    for x in range(0, 5, 1):
        global nani
        if x == 1:
            print("Enter Password:")
            SpeakText("enter password")
            time.sleep(0.3)
            pas1 = input("Password:")
            if pas1 != "!@#$%^&*()qwertyuiop":
                print("Wrong")
                SpeakText("wrong")
                break
            else:
                pass
        elif x == 2:
            print("Enter Word:")
            SpeakText("enter word")
            time.sleep(0.3)
            pas1 = input("Word:")
            if pas1 != "but why do you want me too?":
                print("Wrong")
                SpeakText("wrong")
                break
            else:
                pass
        elif x == 3:
            print("Enter Passcode:")
            SpeakText("enter passcode")
            time.sleep(0.3)
            pas1 = input("passcode:")
            if pas1 != "You asking me for it? Why program?":
                print("Wrong")
                SpeakText("wrong")
                break
            else:
                pass
        elif x == 4:
            nani = 1
            break
            




def speak():
    print("Speak")
    try:
        with sr.Microphone() as source2:
            r.adjust_for_ambient_noise(source2,duration=0.7)
            audio2=r.listen(source2)
            MyText = ""
            try:
                MyText=r.recognize_google(audio2)
            except sr.UnknownValueError as u:
                pass
            MyText=MyText.lower()
            print("Stop")
            time.sleep(0.2)
            return MyText
    except sr.RequestError as s:
        print("an error occur")

if nani == 0:
    time.sleep(0.3)
    a = input("What is your name?\n")
    print("Hello," + a)
    var12345 = "Hello," + a
    SpeakText(var12345)
    time.sleep(0.3)
    print("I am BayMax, your personal assistant")
    SpeakText("I am BayMax, your personal assistant")
    time.sleep(0.5)
    print("How may I help you?")
    SpeakText("How may I help you")
    time.sleep(0.3)
    print("I can help you improve your social and physical well being,and I can give a few suggestions to help you in the future. Happy to help! Ask me anything!")
    SpeakText("I can help you improve your social and physical well being. And I can give a few suggestions to help you in the future. Happy to help! Ask me anything!")
    
    while True:
        oof = speak()
        if "help" in oof:
            print("How do you need help?")
            SpeakText("How do you need help")
            time.sleep(0.3)
            oof= speak()
            if "angry" in oof:
                print("Why are you angry? Is it because something happened, or something someone did to you?\n Say 1 For Something Happened\n Say 2 For Someone Else Did Something")
                SpeakText("Why are you angry? Is it because something happened, or something someone did to you? Say 1 For Something Happened or Say 2 For Someone Else Did Something")
                time.sleep(0.3)
                var1 = speak()
                
                if "1" or "2" in var1:
                    print("If someone did something to you, or something happened, just forget that incident and move on. Escalating the matter wont do any good")
                    SpeakText("If someone did something to you, or something happened, just forget that incident and move on. Escalating the matter wont do any good")
            elif "sad" in oof:
                print("Okay!")
                SpeakText("Okay!")
                print("Are you sad about something you did, or something someone else did?\n Say 1 for You did something \nSay 2 For someone else did something.")
                SpeakText("Are you sad about something you did, or something someone else did? Say 1 for You did something or Say 2 For someone else did something")
                var1 = speak()
                if "1" in var1:
                    print("It is something you did, try and fix it by apologizing.")
                    SpeakText("It is something you did, try and fix it by apologizing. Resolve the situation and move on")
                elif "2" in var1:
                    print("It is something someone else did, think about it with a calm mind. Take a deep breath and take the first step to try and fixing the problem")
                    SpeakText("It is something someone else did, think about it with a calm mind. Take a deep breath and take the first step to try and fixing the problem")
            
            elif "stress"  in oof:
                print("Be Calm, organise your work that you have to do, take deep breaths, start doing the easy work, take breaks in between and if needed, ask for help from your peers")
                SpeakText("Be Calm, organise your work that you have to do, take deep breaths, start doing the easy work, take breaks in between and if needed, ask for help from your peers")
                time.sleep(0.3)
        elif "joke" in oof:
            stJokes=["Two cows are standing in a field. One says to the other: Are you afraid of the mad cow disease. The other says: No it does not because I am a horse",'Mother: How was your first day of School. Son: First Day! You mean I have to go again tomorrow?','Teacher: "Kids, what does the chicken give you?"Student: Meat!,Teacher: Very good! Now what does the pig give you?,Student: Bacon!,Teacher: Great! And what does the fat cow give you?Student: Homework!"',
            "My friend thinks he is smart. He told me an onion is the only food that makes you cry, so I threw a coconut at his face.","When does a joke become a dad joke?. When the punchline is a parent.","How does NASA organize a party? They planet.","How many tickles does it take to get an octopus to laugh?Ten tickles.","What did one toilet say to the other?You look flushed."]
            SpeakText(random.choice(stJokes))




	
        


		
	
	




