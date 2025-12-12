Testing Plan — 

1. Overview
Describe in several sentences what this document is and what it will cover

---

2. User Stories and Acceptance Criteria

User Story 1:  
- Acceptance Criterion 1 
    - Requirement(s): Button that shifts the character into a bullet, timer that reverts bullet back to normal player
    - Purpose: The player should be able to transform into a bullet and avoid obstacles they may encounter through this form.
    - Test Case:
        Feature: Transformation into bullet and transformation back into human
        Test: I would test the transformation function to make sure it transforms in the first place and for the right amount of time.
        Expected Result / Behavior: The player should be turned into a bullet for 5 seconds and then turn back into a human.
        Automation Candidate: This should not be automated because there is not much variation in the testing

- Acceptance Criterion 2 
    - Requirement(s): Visual display of countdown with numbers changing, lines up with actual activation of bullet form
    - Purpose: The player should be able to see how long they are going to be in their bullet form so that the game feels more intuitive.
    - Test Case:
        Feature: Temporary display that shows the timer of how long the user is going to be in bullet form
        Test: I would first transform into the bullet and look at the timer.
        Expected Result / Behavior: The timer should pop up at the same time the person is transformed into the bullet, and the timer should properly line up with when the user transforms.
        Automation Candidate: This should not be automated since there is also not much variation and it is likely a less than 10-try test.


User Story 2:  
- Acceptance Criterion 1 
    - Requirement(s): The bullet should have proper movement, user input is allowed and is seamless
    - Purpose: The user can actually have a way to progress in the game since they can move around obstacles and go forward while in bullet form.
    - Test Case:
        Feature: The user will automatically move forward in bullet form and arrow keys will adjust the direction.
        Test: I will simply transform into the bullet, and press the arrow keys to test the input.
        Expected Result / Behavior: The expected result is that the bullet should move forward automatically and the arrows should adjust the trajectory accordingly and smoothly.
        Automation Candidate: This should not be automated because again the test is quite arbitrary and there isn't much variation in it.

- Acceptance Criterion 2 
    - Requirement(s): There is a loss of health when the user hits an obstacle, when the health hits 0 there should be a death screen
    - Purpose: The player gets adequate feedback when they hit something, making an actual challenge in the game.
    - Test Case:
        Feature: There is a death screen when the user actually dies and hits something, the health visually goes down (and goes down in the backend) 
        Test: I will run into an obstacle to see what happens when I do.
        Expected Result / Behavior: The game should properly lower the health when I hit an obstacle as long as my health isn't 0, and if it IS 0, it should show the death screen.
        Automation Candidate: This should not be automated because it is too abstract to properly have a computer do it for me, and there's not a ton of variation in what I am doing.


User Story 3:  
- Acceptance Criterion 1 
    - Requirement(s): NPCs appear in the world; player talks to them in human form; prompt button works
    - Purpose: The player should be able to get story context and interact with characters so the world feels alive.
    - Test Case:
        Feature: NPC interaction system
        Test: I will shift into human form, approach and NPC, and press the interaction button to see if there's dialogue
        Expected Result / Behavior: When I get close enough to the NPC in human form, there should be an indicator or prompt that will pop up dialogue when clicked.
        Automation Candidate: This shouldn't be automated since NPC placement and interaction are visual and don't vary much between tests.

- Acceptance Criterion 2 
    - Requirement(s): Dialogue box or lore panel appears; story content displays properly, text is readable
    - Purpose: The player gets narrative details that explain their character, the curse, and the world.
    - Test Case:
        Feature: Dialogue or lore display system.
        Test: I will trigger a dialogue event and read through the displayed text to confirm it's showing properly.
        Expected Result / Behavior: The dialogue box should appear cleanly, show correct text, and progress through lines of dialogue.
        Automation Candidate: This should not be automated since verifying story is mostly a visual test and it's suited for automation.

---

3. Boundary and Edge Testing

Boundary / Edge 1:  
    - Requirement(s): Bullet form lasts exactly 5 seconds.
    - Purpose: Make sure timer doesn't end too early or late

    - Test Case 1:
        Upper Boundary: 5 seconds + small offsets
        Testing data used: < 4.9s, 5.0s, 5.1s >
        Expected Result / Behavior: Player should still be bullet; player should revert to human; player should already be human
        Automation Candidate: This shouldn't be automated since verifying timing drift is visual and frame-dependent

    - Test Case 2:
        Lower Boundary: Timer values approaching 0
        Testing data used: < 0.1s , 0s , -0.1s >
        Expected Result / Behavior: bullet should still be active; player should revert immediately; negative time should never happen
        Automation Candidate: No since it's a one time thing and is a visual aspect without variation.


Boundary / Edge 2:  
    - Requirement(s): Health decreases correctly
    - Purpose: Make sure health doesn't drop below zero and death triggers when it should

    - Test Case 1:
        Upper Boundary: Health just above zero
        Testing data used: < 1HP, 0HP, -1HP >
        Expected Result / Behavior: Collision should reduce to 0, death screen should trigger right away, negative HP should never happen
        Automation Candidate: It shouldn't be automated since it's very visual and isn't much variation in it.

    - Test Case 2:
        Lower Boundary: Starting health near max
        Testing data used: < max - 1, max, max + 1 >
        Expected Result / Behavior: max - 1 and max should be normal and not have any effect, max + 1 shouldn't happen
        Automation Candidate: No since it's a one-time test.


Boundary / Edge 3:  
    - Requirement(s): Interaction works only the correct distance
    - Purpose: Ensure the interaction radius isn't too big or small

    - Test Case 1:
        Upper Boundary: Just outside the interaction radius
        Testing data used: < r - 0.1, r, r + 0.1 >
        Expected Result / Behavior: Interaction should work, interaction should work, interaction shouldn't trigger
        Automation Candidate: No since it's a visual test and isn't much variation for multiple tests.

    - Test Case 2:
        Lower Boundary: Inside the radius, but very close
        Testing data used: < 0, very close, normal distance >
        Expected Result / Behavior: interaction should work, very close and normal distance should behave the same
        Automation Candidate: No since there's still not much variation in any of the cases.

---

4. Automated Test List
Which tests were candidates for Automation?  
For each candidate, which kind of automated testing is recommended:  
repetitive, rule-based, or high-volume?

There weren't any candidates for automation simply because there is no need for repetitive tests and many of them would be abstract or visual aspects of the game.