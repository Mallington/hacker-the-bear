Hacker the Husky

By Alex, Alfi, Mathew, Ross and Tom\
For hardware code see the repository [Hacker The Hardware Bear (Github)](https://github.com/Mallington/Hacker-The-Hardware-bear).

## Motivation

Part of Durham County Council’s adult social care services includes improving the daily living of elderly residents who have either mobility issues or mental health problems. However, the cost of these social care projects and personal care assistants is ever-increasing, due to an ageing population. In the year 2018/19, more than 840 000 people received publicly funded long-term adult social care. Clearly, the demand is huge, and so assistive technology is implemented to combat these issues while keeping costs to a minimum. This relieves pressure on adult social care budgets. An estimated 1.1-1.7 million people in the UK are currently supported by assistive technology, solving a variety of problems.

## What we wanted to achieve

Our idea is to create a communication-focused companion to combat loneliness in the elderly, especially those showing early signs of dementia. Many individuals in this category live alone, and therefore have little opportunity to have a conversation. Age UK report that over a million older people say they go over a month without talking to a friend, neighbour, or family member. It is possible that this lack of conversation could lead to a deterioration of their memory. Our device should promote a daily conversation that forces the user to interact with the toy, by recounting their activities throughout the day, for example. The Alzheimer’s Society claims that keeping the brain active by doing these sorts of exercises can improve memory and retain information for longer.

The device should follow some fundamental aims:

    • It should be easy to use
    • It should be follow some basic word triggers to execute commands and respond with one of a list of phrases.
    • It should detect a cry for help, to trigger a correspondence between the user and a family member / emergency services
    • Give reassurance to family members that their loved one can find comfort with this assistive technology

## How we achieved this

Alex and Matt resourced a cuddly puppy toy from a local charity shop. Matt and Ross proceeded to tear apart said toy and insert various components into its stuffing, including servos controlled by a Raspberry API. Meanwhile, Tom created a speech-to-text (STT) as well as a TTS protocol for conversation between the user and the toy. This used a web-scraped API for the Mitsuku chatbot. Alfi looked at how we can store the data in the cloud and Ross investigated how to relay information to the front end via Twilio, which Alex looked into.

Eventually, the device should address the aims via the following:

    • Being a verbal diary and conversationalist
    • Detecting when user says trigger word (“sad”, “lonely”, “depressed”, etc.) and prompts user to decide whether they want the bot to contact family members
    • Encouraging user to recount more details of anecdotes, etc.
    • Dancing every now and then
    • 5% chance of reminding user to drink more water

## Technologies used

    • Twilio: To send SMS messages to family members, including daily updates. These updates are short, but will contain a link to further information hosted on the website that will show how many times the user has interacted with the toy, outlier times, and average mood based off a score that the bot assigns the user each day
    • Google Cloud Platform: The server and database are held in the cloud
    • Google’s Text-To-Speech API: Used in the hard-coding of the bot
    • Domain.com: Got the domain for the website here

## Challenges we ran into

Initially, we thought we could use the Google Home Mini for the microphone / speakers. However, we realised this would involve using Google’s own speech recognition software, and thus requiring the user to say Google’s start-up command (“OK Google”). This would then go against one of our key aims which is to make the technology as easy to use as possible, given the target audience.

Another problem we found was that the version of Python that the Raspberry Pi was running didn’t support some of the code, so some updates needed to be made.

Trying to fit the servos into the stuffed toy proved problematic, so a supportive frame had to be fitted inside so that the arms could be made to move. We built the frame out of chopsticks and zip ties.

We also abandoned the idea of implementing mongoDB into our database structure in favour of Google’s Cloud platform.

The microphone / speakers we had available to us either wouldn’t connect via Bluetooth or used a 3.5mm jack input which also wasn’t supported on the Raspberry Pi. So, for the purposes of the demonstration, we will just use a laptop for the peripherals to hook up to.

Background noise was also an issue the team had to resolve in order for the voice recognition software to work correctly.

Finally, the lag between speech detection and response was initially too large for the interaction to be considered a conversation. Hence, some tweaking was necessary in how the components communicated with each other. This sped up the process dramatically.

Hacker was originally supposed to be a bear, but the only stuffed toy available at Oxfam was a husky puppy. We prefer it this way anyway...

## What's next for Hacker the Husky

There is clearly room for machine learning implementation in the design. This would improve performance and reliability, especially in reading moods taking appropriate courses of action. We will also create a more robust physical product, whose movements are more realistic.

## We hope...

That in the future this type of assistive technology can be used by older people to comfort them and act as a verbal diary, possibly lowering the risk of developing types of dementia, and thus lowering the emotional and financial pressures on families and carers.
