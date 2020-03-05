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

* Github Code: `https://github.com/LambdaSchool/ios-pt2-bw4-lock-key-robert`
* Github Proposal: `https://github.com/Keffury1/ios-build-sprint-project-proposal`
* Trello/Github Project Kanban: `https://github.com/LambdaSchool/ios-pt2-bw4-lock-key-robert/projects/2`
* Test Flight Signup (Recommended): `<insert beta signup link here>`
* YouTube demo video (Recommended): `<insert video url here>`

## Hero Image

`(/Users/bobbykeffury/Development/Lambda/Sprints/Build Sprint - 4/Lock & Key/Lock & Key/Screenshots/Opening.png)`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

`Alerts Interacting together in the SharedController.`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

`Understanding In App Purchases. I was able to study and find the right resources to help explain.`
  
3. Share a chunk of code (or file) you're proud of and explain why.

`It was at this moment I truly understoon functions and passing information.`
  
  func addRiddleAlert(riddle: String, answer: String, clue: String, viewController: UIViewController, button: UIButton?, gesture: UIGestureRecognizer?, view: UIView?, segue: String, audioPlayer: AVAudioPlayer?) {
      
      let riddleAlert = UIAlertController(title: riddle, message: "", preferredStyle: UIAlertController.Style.alert)
      
      if audioPlayer == nil {
          riddleAlert.addTextField(configurationHandler: { (textField) in
              textField.placeholder = "Enter correct answer:"
          })
      } else {
          riddleAlert.addTextField(configurationHandler: { (textField) in
              textField.placeholder = "Enter song name:"
          })
      }
      
      riddleAlert.addAction(UIAlertAction(title: "Submit", style: UIAlertAction.Style.default, handler: { (action: UIAlertAction!) in
          guard let guess = riddleAlert.textFields![0].text?.lowercased() else { return }
          
          if guess == answer {
              riddleAlert.message = ""
              riddleAlert.dismiss(animated: true, completion: nil)
              self.addGestureAlert(with: clue, viewController: viewController, audioPlayer: audioPlayer)
              self.shadowOn(for: button, or: view)
              button?.isEnabled = true
              gesture?.isEnabled = true
          } else {
              CATransaction.setCompletionBlock({
                  self.addRejectedAlert(for: viewController, riddle: riddle, answer: answer, clue: clue, button: button, gesture: gesture, view: view, segue: segue, audioPlayer: audioPlayer)
              })
          }
      }))
      riddleAlert.addAction(UIAlertAction(title: "Home", style: UIAlertAction.Style.cancel, handler: { _ in
          audioPlayer?.stop()
          self.fadeViewOut(view: viewController.view)
          self.segueAfterFadeOut(viewController: viewController, segue: segue)
      }))
      
      viewController.present(riddleAlert, animated: true, completion: nil)
      
      if viewController.traitCollection.userInterfaceStyle == .dark {
          riddleAlert.view.tintColor = .white
      } else {
          riddleAlert.view.tintColor = .black
      }
  }
  
  private func addRejectedAlert(for viewController: UIViewController, riddle: String, answer: String, clue: String, button: UIButton?, gesture: UIGestureRecognizer?, view: UIView?, segue: String, audioPlayer: AVAudioPlayer?) {
      let rejectedAlert = UIAlertController(title: "Wrong Answer", message: "please try again", preferredStyle: UIAlertController.Style.alert)
      rejectedAlert.addAction(UIAlertAction(title: "OK", style: UIAlertAction.Style.cancel, handler: { _ in
          self.addRiddleAlert(riddle: riddle, answer: answer, clue: clue, viewController: viewController, button: button, gesture: gesture, view: view, segue: segue, audioPlayer: audioPlayer)
      }))
      viewController.present(rejectedAlert, animated: true, completion: nil)
      
      if viewController.traitCollection.userInterfaceStyle == .dark {
          rejectedAlert.view.tintColor = .white
      } else {
          rejectedAlert.view.tintColor = .black
      }
  }
  
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

`This is a game made of completely original riddles. Play to stay mentally sharp or to simply enjoy a new game on the market that does what other games have yet to do.  Notice the clean, crisp, fun design in each of the levels. Designed not to be beaten, you will always get your money's worth.`

5. What is your #1 feature?

`Completely custom game of riddles.`
  
6. What are you future goals?

`Publish to the App Store. Begin my next project.`

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
