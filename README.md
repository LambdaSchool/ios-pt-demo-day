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

* Github Code: `<https://github.com/gh04/Unit-1-Countdown-Tracker>`
* Github Proposal: `<https://github.com/LambdaSchool/ios-build-sprint-project-proposal/pull/23>`
* Trello/Github Project Kanban: `<https://github.com/gh04/Unit-1-Countdown-Tracker/projects/1>`
* Test Flight Signup (Recommended): `<insert beta signup link here>`
* YouTube demo video (Recommended): `<insert video url here>`
* Presentation Slides: `<https://docs.google.com/presentation/d/1oV5XA_L9_2taqGVN7GkOf1UfFRVMJ75nvQDh0XiEZp0/edit?usp=sharing>`

## Hero Image

<p align="center">
    <img
        src="https://github.com/davidtwright/ios-pt-demo-day/blob/master/Simulator%20Screen%20Shot%20-%20iPhone%2011%20Pro%20Max%20-%202020-01-13%20at%2023.30.33.png" width="300" alt="Countdowns" />

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

`<The sort feature was our favorite feature to implement because the code for that was very clean and straightforward.>`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

`<Our #1 obstacle was figuring out how to implement persistance on a class that has a timer object inside of it. We created a seperate class that holds all of the data that we needed to persist and then set the class with the timer as a subclass of the new persisting data class.>`
  
3. Share a chunk of code (or file) you're proud of and explain why.

`<I'm proud of how clean and simple the sorting function turned out to be.>`

func sortedCountdowns(from countdowns: [Countdown], with sortStyle: SortStyle? = nil) -> [Countdown] {

    let sortStyle = sortStyle ?? self.sortStyle
    
    switch sortStyle {
    case .time_minToMax:
        return countdowns.sorted { $0.eventDate < $1.eventDate }
    case .time_maxToMin:
        return countdowns.sorted { $0.eventDate > $1.eventDate }
    case .tagName_AToZ:
        return countdowns.sorted { $0.tag.lowercased() < $1.tag.lowercased() }
    case .tagName_ZToA:
        return countdowns.sorted { $0.tag.lowercased() > $1.tag.lowercased() }
    case .eventName_AToZ:
        return countdowns.sorted { $0.eventName.lowercased() < $1.eventName.lowercased() }
    case .eventName_ZToA:
        return countdowns.sorted { $0.eventName.lowercased() > $1.eventName.lowercased() }
    }
}
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

`<Countdowns Tracker is the first countdown app designed with productivity in mind. The ability to tag, edit, filter and sort your countdowns with just the tap of a finger makes creating and managing any number of countdowns a breeze. Let your technology work for you. Countdowns Tracker will help you organize and prioritize all the things you need to do get done in this fast-paced world.>`
  
5. What is your #1 feature?

`<Our #1 feature is the ability to set custom tags along with each countdown and then be able to filter the countdowns by their specific tag name.>`
  
6. What are you future goals?

`<Our future goals are: 1. Redesign the countdown display to make it more visually appealing. 2. Generate an alert outside the app to let the user know when a countdown has expired. 3. Give users the ability to sync calendars to create new countdowns.>`

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
