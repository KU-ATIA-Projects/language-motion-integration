# Human Motion Analysis: Exploring Language-Motion Integration for Motion Editing
* We are in the process of putting code/animations created for this project together. 
The current changes can be found in [MDM](https://github.com/KU-ATIA-Projects/motion-diffusion-model) and [MLD](https://github.com/KU-ATIA-Projects/motion-latent-diffusion).
* Animations can be viewed in the [project page](https://ku-atia-projects.github.io/language-motion-integration/).


## 5.1 Pre-experiments: text-to-motion generation result comparison

<!-- Figure 14: Generated motions of "The person jumps 3 times and sits down". They show insensitivity to numerical values. -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mdm_0.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) Results from MDM. The generated motion is as expected.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mld_0.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) Results from MLD. The person moves 3 steps laterally.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/t2m_gpt_0.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) Results from T2M-GPT. Only two jumps.</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 14: Generated motions of "The person jumps 3 times and sits down". They show insensitivity to numerical values.</figcaption>
</figure>

<!-- Figure 15: Generated motions of ”The man jumped twice, then fell to the ground.” In sequences of action instructions, they often execute only the preceding one. For these three, T2M-GPT successfully executes all the commands while the other two ignore the falling to the ground”. -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mdm_1.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) Results from MDM. The person jumped three times and then stopped, without falling to the ground.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mld_1.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) Results from MLD. The person only jumped once and then stopped.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/t2m_gpt_1.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) Results from T2M-GPT. This person took a small jump in place then fell after a big jump.</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 15: Generated motions of ”The man jumped twice, then fell to the ground.” In sequences of action instructions, they often execute only the preceding one. For these three, T2M-GPT successfully executes all the commands while the other two ignore the falling to the ground”.</figcaption>
</figure>

<!-- Figure 16: Generated motions of ”The person is walking in a curve to the left and then back around
to the right in a curve.” They may lack sensitivity to direction. MLD seems a little confused in
the beginning. Other than that, all three give satisfactory results. -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mdm_2.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) Results from MDM. The generated motion is mostly correct, but the direction is relative to the camera and not to the person.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mld_2.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) Results from MLD. The person turns right, then turns left and walks in a curve to the right (from the camera's perspective), and turns right again.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/t2m_gpt_2.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) Results from T2M-GPT. The generated motion is mostly correct.</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 16: Generated motions of ”The person is walking in a curve to the left and then back around to the right in a curve.” They may lack sensitivity to direction. MLD seems a little confused in the beginning. Other than that, all three give satisfactory results.</figcaption>
</figure>

<!-- Figure 17: Generation motions of ”A person is bouldering.” They may fail to accurately process
texts that are not encompassed within the training set. -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mdm_3.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) Results from MDM. The man looked like he was bent over holding his head forward.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/mld_3.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) Results from MLD. The man looked like he was feet up on the sloping top surface.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_1_pre_experiments/t2m_gpt_3.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) Results from T2M-GPT. The man looked like his body was clenched on something, but still had his feet on the ground.</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 17: Generation motions of ”A person is bouldering.” They may fail to accurately process texts that are not encompassed within the training set.</figcaption>
</figure>

## 5.2 Latent space exploration

### 5.2.1 Latent space exploration of MLD

### 5.2.2 Latent space exploration on MDM
<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_2_latent_space_exploration/MDM/res_interpolation.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Figure 28: Results of interpolation and extrapolation between "A person sits down" and "A person walks to the right". Most results seem normal, except for (d), where the person is walking with crossing legs and sitting on the ground, which is almost impossible for a human.</figcaption>
</figure>


## 5.3 Prompt-based motion editing
<!-- 1a -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample00.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) The person clasps his hands.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample01.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) The person <u>slowly</u> clasps his hands. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample02.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) The person <u>slowly</u> clasps his hands. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 29: Generation results for ”1. Speed and Duration Edits: a. Modifying speed or pacing.” The generated motion is not significantly slower, but Prompt-to-Prompt makes the timing of moving the arms essentially the same in the generated motion. Without Prompt-to-Prompt, the generated motion clasps his hands again after lowering his arms.</figcaption>
</figure>

<!-- 1b -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample04.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) The person clasps his hands.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample05.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) The person <u>slowly</u> clasps his hands. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample06.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) The person <u>slowly</u> clasps his hands. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 30: Generation results for "1. Speed and Duration Edits: b. Changing the duration of the motion."
    After clasping the hand, the generation with Prompt-to-Prompt is indeed lowering the arm a little later while clasping the hand again at the same time as the original motion. In contrast, the generated result without Prompt-to-Prompt is not consistent with the original motion in terms of timing, although the action was still consistent with the prompt.</figcaption>
</figure>

<!-- 2a -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample08.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person walks <u>forward</u>.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample09.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person walks <u>backward</u>. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample10.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person walks <u>backward</u>. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 31: Generation results for "2. Direction and Orientation Edits: a. Changing direction." The two generated results are not significantly different. It is possible that the model understands and performs perfectly for relatively simple orientation adverbs like "forward" and "backward".</figcaption>
</figure>

<!-- 2b -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample12.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person walks <u>forward</u>.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample13.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person walks forward <u>with the upper body facing right</u>. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample14.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person walks forward <u>with the upper body facing right</u>. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 32: Generation results for "2. Direction and Orientation Edits: b. Adjusting orientation." It looks like "walks forward with the upper body facing right" is interpreted as "walks toward the right front". Other than that, the result without Prompt-to-Prompt is even more faithful to the execution of the body to the right command, but this right side is the right side of the camera view rather than the right side of the person. The Prompt-to-Prompt suppresses the execution of the body-facing-right command. </figcaption>
</figure>

<!-- 3a -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample16.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person kicks down with their <u>left</u> leg.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample17.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person kicks down with their <u>right</u> leg. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample18.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person kicks down with their <u>right</u> leg. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 33: Generation results for "3. Body Part and Joint Edits: a. Changing body parts involved." In (a), the person kicks with their right leg, while in (b) the person kicks with their left leg. Again, the model may interpret the orientation as the direction of the camera view rather than the direction of the person. The generation without Prompt-to-Prompt has more other body movements compared to the original motion.</figcaption>
</figure>


<!-- 3b -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample20.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person kicks down with their <u>left</u> leg.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample21.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person kicks <u>high</u> with their left leg. </figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample22.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person kicks <u>high</u> with their left leg. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 34: Generation results for "3. Body Part and Joint Edits: b. Adjusting joint angles." The generation without Prompt-to-Prompt changes the orientation of kicking and not kicking high enough.</figcaption>
</figure>

<!-- 4a -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample24.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person turns to his right and paces back and forth.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample25.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person <u>stands for a while and then</u> turns to his right and paces back and forth. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample26.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person <u>stands for a while and then</u> turns to his right and paces back and forth. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 35: Generation results for "4. Action and Pose Edits: a. Introducing new actions or poses." The generation with Prompt-to-Prompt does stand for a while before turning right, while the generation without Prompt-to-Prompt stands still for a shorter time and turns left rather than right. However, the generation without Prompt-to-Prompt is actually more in line with the prompt.
  </figcaption>
</figure>

<!-- 4b -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample28.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person <u>turns to his right and</u> paces back and forth.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample29.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person paces back and forth. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample30.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person paces back and forth. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 36: Generation results for "4. Action and Pose Edits: b. Removing or replacing actions." The Prompt-to-Prompt makes the direction of movement go from horizontal left-right to front-back. (This is reflected by the movement of the gray surface representing the ground.) This may be the factor that erases the "turns right".</figcaption>
</figure>

<!-- 5a -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample32.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person bends down <u>doing something</u>.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample33.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person bends down <u>picking a box off the ground</u>. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample34.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person bends down <u>picking a box off the ground</u>. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 37: Generation results for "5. Interaction Edits:	a. Interacting with objects." The timing of the body undulation in the Prompt-to-Prompt generation result is exactly the same as the original motion, which is not the case without Prompt-to-Prompt.</figcaption>
</figure>

<!-- 5b -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample36.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person bends down <u>doing something</u>.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample37.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person bends down <u>greeting a kid</u>. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample38.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person bends down <u>greeting a kid</u>. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 38: Generation results for "5. Interaction Edits: b. Interacting with other characters." The generation without Prompt-to-Prompt walks forward, while both the original motion and the Prompt-to-Prompt generation stay in place.
  </figcaption>
</figure>

<!-- 6a -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample40.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person does a dance.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample41.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person does an <u>excited</u> dance. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample42.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person does an <u>excited</u> dance. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 39: Generation results for "6. Emotional and Style Edits: a. Altering the emotional context or intention." 
    The movements are complex and difficult to compare. </figcaption>
</figure>

<!-- 6b -->
<figure style="max-width: 100%;">
  <div style="display: flex;">
    <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample44.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(a) A person does a dance.</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample45.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(b) A person does a <u>robot</u> dance. (with Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
        <div style="flex: 1;">
      <figure style="max-width: 100%;">
        <video controls loop autoplay>
          <source src="animations/5_3_prompt_based_motion_editing/sample46.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        <figcaption>(c) A person does a <u>robot</u> dance. (without Prompt-to-Prompt)</figcaption>
      </figure>
    </div>
  </div>
  <figcaption> Figure 40: Generation results for "6. Emotional and Style Edits: b. Changing the motion style or manner." The movements are complex and difficult to compare.</figcaption>
</figure>

## 5.4 Ablations
* This section presents more and broader results relative to the results presented in the same position in the thesis.
* Arranged from top to bottom, the first row depicts the original motion, while the second and third rows display the edited motions with and without the utilization of Prompt-to-Prompt, respectively. In the fourth row, the edited prompt's self-attention is incorporated into the unconditionally generated outcomes. Progressing from left to right, the Prompt-to-Prompt thresholds are consecutively set at 0.01, 0.02, extending up to 0.10.

### Data filtering approach

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair00_03_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "1. Speed and Duration Edits: a. Modifying speed or pacing." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair04_07_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "1. Speed and Duration Edits: b. Changing the duration of the motion." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair08_11_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "2. Direction and Orientation Edits: a. Changing direction." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair12_15_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "2. Direction and Orientation Edits: b. Adjusting orientation." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair16_19_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "3. Body Part and Joint Edits: a. Changing body parts involved." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair20_23_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "3. Body Part and Joint Edits: b. Adjusting joint angles." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair24_27_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "4. Action and Pose Edits: a. Introducing new actions or poses." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair28_31_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "4. Action and Pose Edits: b. Removing or replacing actions." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair32_35_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "5. Interaction Edits:	a. Interacting with objects." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair36_39_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "5. Interaction Edits: b. Interacting with other characters." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair40_43_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "6. Emotional and Style Edits: a. Altering the emotional context or intention." </figcaption>
</figure>

<figure style="max-width: 100%;">
  <video controls loop autoplay>
    <source src="animations/5_4_ablations/pair44_47_rep00_grid.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Prompt-to-Prompt effects for "6. Emotional and Style Edits: b. Changing the motion style or manner." </figcaption>
</figure>
