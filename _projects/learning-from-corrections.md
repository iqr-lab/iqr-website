---
title: Learning from Corrections
project-tag: learning-from-corrections
description: "Corrections offer an easy way for end-users to teach and collaborate with a robot, while also offering rich information about task constraints. However, these corrections reflect more than just the optimality of the robot behavior, and are subject to additional influences such as task tolerance, physical effort, and the human's subjective expectation of whether the robot will succeed. **How can robots account for these biases so they can learn more effectively from corrections?**"
button-text: More details
tags:
  # - learning from corrections
  # - inverse reinforcement learning
  # - project
authors:
  - anjiabei-wang
  - shuangge-wang
image: images/projects/corrections.png
---

With the continued integration of machines into our everyday lives, the principle of non-technical human teachers being able to effectively communicate with and efficiently train robots becomes increasingly relevant. Current and prior research has looked into how people can train a robot to complete manipulation-based tasks using different modalities or interaction types, such as demonstrations [1] and ranked preferences [2]. Alternatively, a person can monitor a robot as it attempts to complete a task, interceding to provide a \emph{correction} when they deem it necessary to modify the robot's behavior [3,4]. For example, if a robot that is supposed to pick up a mug from the table is moving away from the table instead, a human teacher may offer assistance by correcting the robot's motion and pushing it in the right direction. This correction should inform how the robot behaves in future variations of the task, while also implying how the robot should **not** behave (i.e., the behavior that prompted the teacher to intercede in the first place). 

From a physical human-robot interaction perspective, corrections are a natural method for collaboration and communication between humans and robots [5]. For non-technical users, it is easier to express their intent by directly interacting with the robots, as opposed to programming them. Furthermore, corrections put the human in the role of a supervisor rather than teacher, where they only step in as needed rather than try to teach the robot from scratch. This reduces the amount of data required to improve task performance and increases the efficiency of robot learning [6].

From a ML perspective, corrections have the potential to provide rich information for a robot to learn an optimal model of the task objective. Based on the initial behavior of the robot, a human's correction of that behavior can indicate what the robot did right or wrong, and how to avoid making similar mistakes in the future. However, corrections are complicated to interpret. Bayesian Inverse Reinforcement Learning (BIRL) provides a method for learning a reward function that maximizes the likelihood of the teacher's feedback [7, 8, 9]. Yet, this approach requires that we have a model of how the human feedback is influenced by the task objectives. When learning from corrections, there are other conflating influences such as the **abruptness** of the corrections (caused by the human's binary decision of whether or not to correct the robot's behavior) and the subjective **bias** that influences the teacher's belief over whether or not the robot will succeed at the task. This decision to interrupt and modify the robot's motion may occur after the robot has made a mistake or in anticipation of a future mistake that has not even occurred yet, and may be biased by the robot's previous behavior [10]. Prior work has focused on interpreting and learning from corrections [11, 12, 13], but has not looked into how the teacher decides to intervene and provide a correction in the first place.

The key challenge we address is how to isolate the influence of task objectives on corrections from other conflating influences. To do this, we need to first model the effects of these influences on corrections. 

In this abstract, we hypothesize the effects of three variables (legibility, task tolerance, and physical effort) on corrections and formalize them as predictive models. We then propose a user study to evaluate these models. Finally, we discuss how these models can be used to improve ML algorithms in future work.
