# iOSPT Demo Day

## Requirements

1. Fork and clone the repository
2. **Add your presentation content**
    https://docs.google.com/presentation/d/1ez1ifI3vLrlGbp_RAvRziGm5MAYjdGK5rjjAg-ONeWA/edit?usp=sharing

## Links

* Github Code: https://github.com/hai666l/Note-Tracker
* Github Proposal: https://github.com/hai666l/ios-build-sprint-project-proposal
* Trello/Github Project Kanban: `<insert trello board here>`
* Test Flight Signup (Recommended): `<insert beta signup link here>`
* YouTube demo video (Recommended): `<insert video url here>`

## Hero Image



## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    My favorite feature to implement was the Theme Selection, it took a while but I learned a lot in how to successfully edit the apperances of buttons, text, and backgrounds appwide

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    Themes often wouldn't apply to everything we wanted them to, there are still a few visual bugs but for the most part these were fixed by linking them from the storyboard and doing edits to code 
  
3. Share a chunk of code (or file) you're proud of and explain why.

       `@IBAction func colorTapped(_ sender: UIButton) {
        if sender.accessibilityLabel == "font" {
            for index in 0...identifiers.count {
                if sender.accessibilityIdentifier == identifiers[index] {
                    Theme.current.fontColor = colors[index]
                    return;
                }
            }
        }
        if sender.accessibilityLabel == "button" {
            for index in 0...identifiers.count {
                if sender.accessibilityIdentifier == identifiers[index] {
                    Theme.current.buttonColor = colors[index]
                    return;
                }
            }
        }
        if sender.accessibilityLabel == "background" {
            for index in 0...identifiers.count {
                if sender.accessibilityIdentifier == identifiers[index] {
                    Theme.current.backgroundColor = colors[index]
                    return;
                }
            }
        }
    }`
    This code is used for setting the theme from 27 possible different uibutton choices, it takes two arrays and compares their values to find out which specific label and identifier was responsible for sending the colorChanged event
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    Our app is a note taking app for everyone, but focused towards creative people who want a simple and completely customizable experience for their note taking app
  
5. What is your #1 feature?

    Theme color selection from many different choices
  
6. What are you future goals?

    Add a view for selecting a color from a custom rgb slider to be used as a custom theme color.
    Pinning, archiving, trash storage for notes
    Timestamps in the tableViewCells


## Required Slides (Add your Keynote to your PR)

1. App Name / Team Slide
2. Elevator Pitch
3. Your #1 Feature (Customer facing — what can I do with your app?)
4. Future Goals

## Slide Requirements

1. 50 pt font minimum
2. Be concise — don't write sentences/paragraphs (put these in your slide notes for speaking)
3. 3-6 bullets maximum per slide
4. Do the squint test (can you read the text if you squint, if so, make the font bigger)
6. Images are always welcome
7. Do the Grandma Test (Would your Grandma understand you?)

### Optional Slides

1. Blooper: What's a funny bug or blooper? (screenshots/GIFs please)
2. Revenue Model: If the app was your sole source of income, how would you monetize it?

## Presentation Format

**7 minutes/team**

* 4 minute presentation (5 minute hard cap)
* 3 minutes of questions

We have ~12 teams presenting today — please practice your presentation with a timer (as a team), and make sure you fit within the time limit.

Plan on having one person present the slides and live demo. Please practice your presentation in front of a mirror or with your team 2-5 times. Have the app running and visible (Simulator or QuickTime) so you can quickly transition between slides and live demo.

* App Name / Team Slide (30 seconds)
* Elevator Pitch Slide (30 seconds)
* Your #1 Feature (30 seconds)
* Live Demo (2 minutes)
* Future Goals (30 seconds)
* Questions (3 minutes)
