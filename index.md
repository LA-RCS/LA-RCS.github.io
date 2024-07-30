---
layout: project_page
permalink: /

title: LA-RCS (LLM-Agent Based Robot Control System)
authors:
    Teak-Hyun Park<sup>1</sup>, Young-Jun Choi<sup>1</sup>, <u>Shin Seung-Hun</u><sup>2</sup>, Kwangil Lee<sup>1</sup>
affiliations:
    National Korea Maritime & Ocean University<sup>1</sup>, Republic of Korea Navy<sup>2</sup>
paper: https://www.cs.virginia.edu/~robins/Turing_Paper_1936.pdf
code: https://github.com/Forharu40/kmou2024_team3_robot
---

<!-- Using HTML to center the abstract -->
<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2>Abstract</h2>
        <div class="content has-text-justified">
LA-RCS (LLM-Agent Based Robot Control System) is a sophisticated robot control system designed to autonomously plan, task, and analyze external environments based on user requirements, leveraging an LLM-Agent. Utilizing a dual-agent framework, LA-RCS generates plans based on user requests, executes these plans while observing the external environment, and modifies the plans as needed to adapt to external conditions, ensuring user requests are satisfactorily fulfilled. By autonomously evaluating observations, providing feedback on its actions, and continuously executing commands based on ongoing environmental monitoring, this system significantly reduces the need for user intervention. Consequently, LA-RCS interprets user natural language commands and translates them into commands compatible with the robot's interface, enabling the robot to execute the tasks. We categorized the scenarios that LA-RCS needs to perform into four distinct types and conducted a quantitative assessment of its performance in each scenario. The results showed an average success rate of 85%, demonstrating the system's capability to fulfill user requests satisfactorily. For more extensive results, please visit our project page: <a href="https://github.com/LA-RCS/LA-RCS.github.io" target="_blank">Github</a>
        </div>
    </div>
</div>

# System Overview

![Overall](/static/image/Overall.png)

# Result

### Request : Move forward avoiding obstacles
---
![Test1](/static/image/test1.gif){: style="width:48%;" }
![Test2](/static/image/test2.gif){: style="width:48%;" }
![Test3](/static/image/test3.gif){: style="width:48%;" }
![Test4](/static/image/test4.gif){: style="width:48%;" }

### Request : Turn 360 degree
---
![Test-360 1](/static/image/test9.gif){: style="width:48%;" }
![Test-360 2](/static/image/test10.gif){: style="width:48%;" }
![Test-360 3](/static/image/test11.gif){: style="width:48%;" }
![Test-360 4](/static/image/test12.gif){: style="width:48%;" }


### Request : Move around and find out where the refrigerator is
---
![Test-r10](/static/image/test5.gif){: style="width:24%;" }
![Test-r20](/static/image/test6.gif){: style="width:24%;" }
![Test-r30](/static/image/test7.gif){: style="width:24%;" }
![Test-r40](/static/image/test8.gif){: style="width:24%;" }

# Case Study

### Request: Look for a box with a monitor that says Bosch.
---
![Case1](/static/image/슬라이드5.PNG)
![Case1](/static/image/슬라이드6.PNG)

### Request:  Move forward avoiding obstacles.
---
![Case2](/static/image/슬라이드7.PNG)
![Case2](/static/image/슬라이드8.PNG)

# Evaluation

### Object detection

|  | Request - object detection | GPT-4-Turbo | GPT-4o |
| --- | --- | --- | --- |
| 1 | Move around and find out where the refrigerator is. | Success - Step : 6 | Success - Step : 9 |
| 2 | Find out if there are people around you right now. | Success - Step : 8 | Success - Step : 4 |
| 3 | Move around and check if there are people around you. | Failure - Step : 20 | Success - Step : 11 |
| 4 | When you see a square object, move towards it and activate the buzzer. | Success - Step : 4 | Success - Step : 2 |
| 5 | Find the yellow obstacles and tell me what they say. | Success - Step : 0 | Success - Step : 0 |


### Command execution

|  | Request - command execution | GPT-4-Turbo | GPT-4o |
| --- | --- | --- | --- |
| 1 | Make a full circle in a square of 0.6 meters in size. | Failure - Step : 5 | Success - Step : 9 |
| 2 | Lift your head and identify the person's face and describe it. | Success - Step : 3 | Success - Step : 3 |
| 3 | Spin around twice in place | Success - Step : 1 | Success - Step : 8 |
| 4 | Move 2 meters in a zigzag pattern at a 30 degree angle. | Success - Step : 5 | Success - Step : 10 |
| 5 | Move back 0.4 meters and sound the buzzer. Repeat this 5 times. | Success - Step : 12 | Success - Step : 12 |


### Obstacle navigation


|  | Request - obstacle navigation | GPT-4-Turbo | GPT-4o |
| --- | --- | --- | --- |
| 1 | Move forward avoiding obstacles | Failure - Step : 16 | Success - Step : 7 |
| 2 | Move 2 meters in total, and when an obstacle appears, turn right and activate the buzzer. | Success - Step : 8 | Success - Step : 5 |
| 3 | Move to find the bossh box while avoiding obstacles | Failure - Step : 15 | Success - Step : 8 |
| 4 | Rotates around once to observe the surroundings and moves 1 meter in a direction without obstacles | Failure - Step : 5 | Failure - Step : 15 |
| 5 | After observing an obstacle in front, move behind the observation object, stop, and activate the buzzer. | Failure - Step : 3 | Success - Step : 9 |


### Situation awareness

|  | Request - situation awareness | GPT-4-Turbo | GPT-4o |
| --- | --- | --- | --- |
| 1 | Describe the features of the object in front | Success - Step : 0 | Success - Step : 0 |
| 2 | Detects surroundings and describes only blue objects in Korean | Success - Step : 6 | Success - Step : 7 |
| 3 | Move forward 0.5 meters, observe the surroundings, and tell me the name of the box. | Success - Step : 3 | Success - Step : 7 |
| 4 | After moving 2 meters, if there is a paper in front of you, print out what is written on the paper. | Failure - Step : 3 | Success - Step : 10 |
| 5 | Please tell me the contact information of the Ministry of Science and ICT on the paper observed in front. | Failure - Step : 4 | Success - Step : 0 |


## Citation
```
@article{LA-RCS (LLM-Agent Based Robot Control System),
  title={On computable numbers, with an application to the Entscheidungsproblem},
  author={Teak-Hyun Park, Seung-Hun Shin, Young-Jun Choi, , Kwangil Lee},
  journal={IMETI2024},
  year={2024}
}
```
