# thesis
# thesis

## PAPYRUS run sequence
### inside src/main

### TRAIN

#### T01_Process_training_tears_using_cubes_match.ipynb
RUN1 - run training on 1st piece of PX303
	- consider num of cols (8) and num or rows (4)
	- consider enrichment factor (1=no enrichment) and tolerance factor (5= up to 50 px tolerance) for generation of matches
	- run train (may re-use previous batch of matches if running multiple times)
RUN2 - run training on 2nd piece of PX303
	- consider num of cols (8) and num or rows (4)  - note the offset of the initial crop
	- consider enrichment factor (1=no enrichment) and tolerance factor (5= up to 50 px tolerance) for generation of matches
	- run train (may re-use previous batch of matches if running multiple times)
RUN3 - run training on 3nd piece of PX303
	- consider num of cols (8) and num or rows (4)  - note the offset of the initial crop
	- consider enrichment factor (1=no enrichment) and tolerance factor (5= up to 50 px tolerance) for generation of matches
	- run train (may re-use previous batch of matches if running multiple times)

#### T02_parse_matches_SYNT.ipynb
Convert the pairs.csv into votes.csv
— Due to the large size of of votes - better to run the 2nd phase only after running the 18 and 16
Convert the votes.csv into flipped.csv

#### continue to run training steps using R04, R05, R06


### TEST (real fragments set)
#### R01_Pre_process_validation_set.ipynb
Run this once in order to crop and rotate all the validation set according to needed

#### R02_Process_validation_tears_using_cubes_match.ipynb
run the validation on the cropped set utilising the crops.csv and the crop folder from previous stage

#### R03_parse_matches.ipynb
Convert the pairs.csv into votes.csv
— Due to the large size of of votes - better to run the 2nd phase only after running the 18 and 16
Convert the votes.csv into flipped.csv

#### R04_Align_fragments.ipynb
Align the pieces and get additional information into the enriched.csv

#### R05_16_Random_Forest_Clean_Prints_and_write_output.ipynb
Run a pre-trained random-forest in order to identify the matching fragments into final.csv

#### R06_UX.ipynb
Use it in order to prepare the results for display - by concatenating the front and drawing the lines on it and preparing the thumbnails
