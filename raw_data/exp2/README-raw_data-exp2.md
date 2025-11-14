# Files
## drawing_timing.xlsx
How long each participant spent drawing a 3D sketchmap (column: VR Time) and 2D sketchmap (column: Hand Time). Values come from manual timing of the experimenter. Unit: seconds.

## unity_timing.csv
How long each participant spend in the learning task (flying the drone). Participants were able to start/stop the flight, so the times differ. The file records how long (in total) each landmark was within the field of view of each participant.


## NASA-TLX folder
Results of the NASA Task Load Index, obtained using the NASA-TLX mobile app presented on the tablet (iPad). Link to app: https://humansystems.arc.nasa.gov/groups/TLX/

Description of rows in this file:

- STUDY NAME: same in all files

- STUDY GROUP (Hand vs VR): the experimental condition
(a hand-drawn 2d sketchmap vs a VR-drawn 3d sketchmap)

- SUBJECT ID: participant ID. There are two files for each participant, one for each condition (STUDY GROUP column)

- TRIAL: each participant drew 2 sketchmaps, in a counterbalanced order. This column specifies whether this files describes the first or the second drawing. In combination with STUDY GROUP, it can be determined whether the given participant draw the 2D sketchmap as first or as second.

- TRIAL DATE TIME: date of data collection


## questionnaire.xlsx
Results of the questionnaire collected via Google Docs on a tablet, at the beginning of the study.

Description of columns:

- Assigned ID: participant ID (SUBJECT ID in the NASA-TLX files).

- Experience with VR headsets
A single-choice question with 3 possible answers: 
	* I never used VR
	* I used VR <10 times in my life
	* I used VR 10 times or more in my life but don't use it regularly
	* I use VR regularly

- Example [A] and Example [B]: responses to practice items at the beginning of the test.

- Score: score of the Urban Layout Test extracted from the battery of tests by Berkowitz et al.
paper:		https://doi.org/10.3389/fpsyg.2020.609363
repository: 	https://osf.io/jf5mx/
test pdf:	https://osf.io/h3mr6

For each Urban Layout item (numbered 1-10), participant needs to specify which of 4 presented views corresponds to arrow A and to arrow B. Each participants gives two answers to each item.
These individual answers are recorded as 1 [A], 1 [B] (for layout 1), 2 [A], 2 [B] etc.

The score is calculated by taking the correct number of responses (out of 20 items).

- Total Time (minutes) was calculated by subtracting 'Timestamp' (when the questionnaire was finished) from 'StartTime'.

## scoring_sheets folder
The folder with excel spreadsheets from manual scoring of sketch maps. Participant ID is in the file name. We keep the excel format because of comments/annotations around edge cases.

##  sketchmaps folder
The folder with original drawings.


# Software versions used:

Unity version --> 2022.3.11f1

Gravity Sketch version --> 6.1.6


# Notes on Participants:

*those marked with '!' were excluded from the analyses*

102 --> has drawn 2 sketches next to each other in gravity sketch. first one was in 2D somehow and she was not satisfied about and after understanding some tools on how to control the triggers, she drew another one in 3D but mentioned she now Forgot!

103 --> mentioned that drawing in VR was easier to memorize because you draw in the same environment you saw before but in paper was harder to remember the turns.

104 --> Started by drawing the Route

108 --> Drew kind of 2D in sketch gravity, it's visible from the starting point

111 --> Drew kind of 2D in sketch gravity, it's visible from the starting point

115 --> Started by drawing the Landamrks and refere their location to each other

! 118 --> He took about an hour for the test. It was a bit challenging explaining him everything and makeing sure he understands. Like he was just pressing everz buttons at once and wasnt pazing attention to what i am saying and what the tutorial is telling him.

119 --> Started by drawing the route and it was easier later to put every thing. Nice technique.

! 123 --> drew the route in the backward direction differently than in forward direction

! 129 --> Had a bad motion sickness, needed to take a 10 minutes break while being in the environment and couldn't be able to finish the last 30 seconds of the route but was able to point to the objects' location and uderstand the environment, draw it in paper but i said she doesn't have to draw in VR bcs she was sick.

! 131 --> Bad motion sickness, couldn't take the whole trip. I asked her to draw on paper

134 --> In VR, he drew 3D but from single angle, same as in paper.

135 --> chose 2D bcs he told it's hard to draw in 3D, he is a pilot.