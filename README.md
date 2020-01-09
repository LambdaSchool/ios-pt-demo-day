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

* Github Code: `https://github.com/LambdaSchool/ios-pt1-bw4-home-mortgate-calculator-corey-michael`
* Github Proposal: `https://github.com/michaelstoffer/ios-pt1-build-sprint-4-project-proposal/edit/master/Answers.md`
* Trello/Github Project Kanban: `https://github.com/LambdaSchool/ios-pt1-bw4-home-mortgate-calculator-corey-michael/issues`
* Test Flight Signup (Recommended): `https://testflight.apple.com/join/4SeWreG2`
* YouTube demo video (Recommended): `<insert video url here>`

## Hero Image

`<Post one screenshot in an iPhone Simulator frame or an iPhone 11 Pro render using placeit.com>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    `Some of the UI Features that make the app more user friendly. Because it makes the app look nice.`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    `The app was crashing when you left the text fields blank and hit the calculate button. We fixed it by removing the amortization schedule algorithm from the calculate button into its own button and this fixed the app so it wouldn't crash anymore. We also added some alerts so if the text fields are empty, they will show an alert letting the user know they forgot to fill something out.`

3. Share a chunk of code (or file) you're proud of and explain why.

    `func textFieldDidBeginEditing(_ textField: UITextField) {
        textField.layer.borderWidth = 2.0
        textField.layer.borderColor = UIColor.systemGreen.cgColor
        textField.layer.cornerRadius = 5
    }`

    `func textFieldDidEndEditing(_ textField: UITextField) {
        textField.layer.borderWidth = 1.0
        textField.layer.borderColor = UIColor.systemGray.cgColor
        textField.layer.cornerRadius = 5
        if textField == homePriceTxtField {
            guard let value = textField.text, !value.isEmpty else { return }
            let doubleVal = (value as NSString).doubleValue
            self.principalAmount = doubleVal
            textField.text = formatCurrencyValue(value: doubleVal)
        } else if textField == downPaymentTxtField {
            guard let value = textField.text, !value.isEmpty else { return }
            let doubleVal = (value as NSString).doubleValue
            self.downPayment = doubleVal
            let percentage = Int((self.downPayment / self.principalAmount) * 100)
            downPmtPercentageLbl.text = "(\(percentage)%)"
            textField.text = formatCurrencyValue(value: doubleVal)
        } else if textField == interestRateTxtField {
            guard let value = textField.text, !value.isEmpty else { return }
            let doubleVal = (value as NSString).doubleValue
            self.interestRate = doubleVal
            textField.text = formatPercentageValue(value: doubleVal)
        } else if textField == loanTermTxtField {
            guard let value = textField.text, !value.isEmpty else { return }
            let doubleVal = (value as NSString).doubleValue
            self.termLength = doubleVal
            textField.text = formatTermValue(value: doubleVal)
        }
    }`

4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    `A quick and easy way to find a monthly payment for a mortgage based on the cost of the house, down payment, interest rate and loan term.`

5. What is your #1 feature?

    `Showing the user how each monthly payment will be applied to the principal of the loan via an Amortization Schedule.`

6. What are you future goals?

    `Selling to Warren Buffet for 1 billion dollars.`

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
