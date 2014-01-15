AnimatedThoughtBotLogo
======================

My main two goals for this project were

1. Use CSS3/HTML5 to recreate an exact replica for a real company's logo
2. Animate parts of the logo using CSS3 Animations with as little javascript as possible

### Phase 1: Brainstorming

![alt text][sketch]

### Phase 2: Planning

After brainstorming, I had a pretty solid idea of what I'd need html wise, so I had to start with the tedious process of sizing the different parts of ThoughtBot's logo. This was actually harder than I thought it would be, because the sizes weren't exact. Does a half-shaded line count towards the section? I mostly used common sense, but I also discovered a few things about the image I saved from ThoughtBot's logo. The robot isn't exactly centered, which drove me a little insane.

![alt text][sizing]


### Phase 3: Implementation

So I learned a lot through this exercise.

- I didn't have to give the arm a -180px initial rotation and could have used `transform-origin: top right;`
- It's super easy to auto center divs with just this:

```css
.buttons{
  position: relative;
  width: 400px;
  left: calc(50% - 200px);
}
```
- Using "joints" for animating the arms and legs worked out really well. Using a skinny `.bone` to rotate on eased te problem that stems from rotating on a corner.
- Create a pause between animations using this formula:

```ruby
actual_animation_duration = desired_iteration_length + desired_pause

actual_step_duration = desired_step_duration * desired_iteration_length / actual_animation_duration
```

See the `.chase` animation for an example.


### Things to do differently/improve

1. Use Sass. I just wanted to practice pure CSS
2. Rotations.
3. Clean up javascript code and make it more modular, especially `Broadcaster` and `startChasing`.

[sketch]: https://github.com/TalkativeTree/AnimatedThoughtBotLogo/raw/master/RobotSketching.jpg "Design Sketch"
[sizing]: https://github.com/TalkativeTree/AnimatedThoughtBotLogo/raw/master/robot_sizing.jpg "Image Sizing"
