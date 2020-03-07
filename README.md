# iOSPT Demo Day

## Requirements

1. Fork and clone the repository
2. **Add your presentation content**
    1. Slide deck (4 required slides)
    2. Links
    3. Answer all questions 
    4. YouTube demo video (1-2 min max)
3. Polish your Github Code repository
    1. Add screenshots and an overview to your GitHub Code Repository
    2. You should make that repository the "Public Portfolio" for your project
    3. Look at [John Sundell's Splash project](https://github.com/JohnSundell/Splash) for inspiration (code, images, GIFs)
4. Create a pull request (PR) and **tag your TL and Instructor**

## Links

* Github Code: `https://github.com/iOSPT5-BW1/Mood-Tracker`
* Github Proposal: `https://github.com/LambdaSchool/ios-build-sprint-project-proposal/pull/51`
* Trello/Github Project Kanban: `https://www.notion.so/3ee4fdd8057a423bb1e1eb3f8282cc6b?v=c7eff0fd505f465a830043392c30af9d`
* Test Flight Signup (Recommended): `<insert beta signup link here>`
* YouTube demo video (Recommended): `https://youtu.be/ETCJeRKu03M`

## Hero Image

`<Post one screenshot in an iPhone Simulator frame or an iPhone 11 Pro render using placeit.com>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    `Adding the Quote API. Before finding the API I was overthinking the process of having to find quotes and pcures and making it all fit together on the screen. Having long quotes, short quotes and making everything look good. That seemed more daunting than implementing the API`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    `Having the tableview and the chart reload after data was added. Both of these were hard to fix and very frustrating. The tableview was resolved using delegates and protocols and the chart was fixed using noification center. It was a fantastic learning experience but it was also very frustrating.`
  
3. Share a chunk of code (or file) you're proud of and explain why.
    ```
    func createObserver() {
        NotificationCenter.default.addObserver(self, selector: #selector(GraphViewController.updateChart(notification:)), name: moodName, object: nil)
        
        NotificationCenter.default.addObserver(self, selector: #selector(GraphViewController.deleteData(notification:)), name: moodDeletedName, object: nil)
    }
    
    @objc func updateChart(notification: NSNotification) {
        let moodController = notification.object as! MoodModelController
        let lastMood = moodController.moods.last
        
        switch lastMood!.emotion.state.rawValue {
        case "angry":
            angryData.value += 1
        case "happy":
            happyData.value += 1
        case "sad":
            sadData.value += 1
        case "excited":
            excitedData.value += 1
        case "annoyed":
            annoyedData.value += 1
        case "meh":
            mehData.value += 1
        default:
            print("Data not found")
        }
        
        numberOfMoodDataEntries = [angryData, happyData, sadData, excitedData, annoyedData, mehData]
        updateChartData()
    }```
    `I hadn't heard of notifications and observers until it was suggested that I add them to the project to help resolve the update issue. I was freaking out about implementing it but I did it. I asked for help and the issue even stumped others but I was able to solve it. `
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    `An app to track your moods. `
  
5. What is your #1 feature?

    `<Your answer here>`
  
6. What are you future goals?

    `<Your answer here>`

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
