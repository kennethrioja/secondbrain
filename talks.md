# Talks

<!-- vim-markdown-toc GFM -->

* [19.10.2023 - Jeffrey Bowers – Deep Problems with NN models of Human Vision](#19102023---jeffrey-bowers--deep-problems-with-nn-models-of-human-vision)
* [12.10.2023 - Dr. Claudia von Bastian – Mechanisms of Cognitive Training and Transfer Effects: Capacity and Efficiency](#12102023---dr-claudia-von-bastian--mechanisms-of-cognitive-training-and-transfer-effects-capacity-and-efficiency)
* [14.09.2023 - BTN – UNIGE Data Science Day](#14092023---btn--unige-data-science-day)
* [08.12.2022 - Chandramallika Basak - Brain-Based Mechanisms of Cognitive Enhancemeents in Aing: Benefits of Computerized Training](#08122022---chandramallika-basak---brain-based-mechanisms-of-cognitive-enhancemeents-in-aing-benefits-of-computerized-training)
* [02.12.2022 - Swiss Reproducibility Network - Preregistration & Registered reports: how to improve the credibility and reproducibility of your research](#02122022---swiss-reproducibility-network---preregistration--registered-reports-how-to-improve-the-credibility-and-reproducibility-of-your-research)
* [11.10.2022 - Cvetomir Dimov - An Integrated Model of Collaborative Skill Acquisition: Anticipation,Control Tuning, and Role Adoption](#11102022---cvetomir-dimov---an-integrated-model-of-collaborative-skill-acquisition-anticipationcontrol-tuning-and-role-adoption)

<!-- vim-markdown-toc -->

# 19.10.2023 - Jeffrey Bowers – Deep Problems with NN models of Human Vision

- His main claim : Similarities bw DNN and humans are greatly exaggerated
- We, humans, recognize objects based on their shape
- Estimates od DNN-human similarity often come from behavioral and brain benchmark studies that do not manipulate IV to test specific hypothesis
- Rather, these benchmarks assess how well DNNs predict brain responses to stimuli that vary along multiple dimensions after averaging over these dimensions of variation :
	- Effectively these benchmarks are observational rather than controlled studies
- See how well your NN predict response
- Activ of model and monkey, and regression bw this and this, then new image, how can I predict activation ?
- "Because I can predict, I can then have a mechanistic model of human brain" BUT correlation is not causation
- Most obvious problem: confounds can drive good predictions
- Geirhos et al., 2019 : if you give to models, for the most part, don't care about shape, but care about texture. BUT human care about shapes. These models recognizing models based on textures have good  brain-score. BUT Texture and shapes are correlated !
- Researchers are interested in reporting similarities rather than differences
- Explainable variance : how much can one brain predict another brain ? I can predict 100% of 4% of the explainable variance
- Caucheteux et al., 2022 : .5 correlation bw GPT2 and "comprehension" (what is comprehension?) on .02% of variance
- Models that recognize based on shape
- Human vision : hwo one can regonize not hollistic but with relations with its related parts
- Face recognition expertise lead to unright face decrease discrimination, takes longer because trained on this
- Biscione et al., 2023 : [MindSet](https://github.com/ValerioB88/mind-set)
- "It's not like the brain? Then ok BUT You have to make the model like the brain" Finding falsification is sufficient
- "You find difference but I need similarity" – reviewers said
- Stop brain-score
- Raking models is misguiding, we don't know why it is better than the other

# 12.10.2023 - Dr. Claudia von Bastian – Mechanisms of Cognitive Training and Transfer Effects: Capacity and Efficiency
- Why cog training doe snot work ?
- Transfer if :
	- Common elements
	- Shared cog processes, functional overlap => WM
- WM expand cog training? Yes and No due to (garbage-in garbage-out) :
	- Lack of active controls
	- Single ability indicators
	- Low stat power (FP, inflated effect sizes)
- Cog train in younger and older adults :
	- Better at proc speed (?), practice effect but no near nor far transfer
	- No cor with motiv, personality or cog-related beliefed
	- **WM training is not a quick-fix solution for reliably boosting WM, EF and intelligence**
	- Reduce effort by using **paradigm-specific** expertise + **stimuli-specific** expertise
- Mechanisms of efficiency in cog training
	- https://www.nature.com/articles/s44159-021-00001-3
	- More efficiently allocate attention, e.g., dual-task; what to prioritize
	- Jiang et al., 2023 :
		- Strong prac effect in the trained taks on precisions but not capacity; no transfer to shape reproduction or change detection
		- When trained, more orientations, suggesting possible interaction bw paradigm-specific and stimuli-specific expertise
		- DDR : Rate of evidence decision + boundary separation : bw different/same + non-decision time : motoric time
- Be comparable on age, gender, but also education and time-allocated for X
- Little to no evidence for experience-based plasticity of capacity
- Cog activities support dev of paradigm-specific and stimuli-specific expertise

# 14.09.2023 - [BTN – UNIGE Data Science Day](https://datascience.unige.ch/en/research/uniges-data-science-days)

- Data Science Seminars : https://datascience.unige.ch/en/research/data-science-seminars - apply
- Learning data : https://datascience.unige.ch/cite/capsules-audio - apply
- Data Science Capsules video : https://datascience.unige.ch/forall/capsules-video - apply
- 4-5th november : undatathon SDG : https://unstats.un.org/bigdata/events/2023/un-datathon/
- Coding Dojo : https://cui.unige.ch/fr/pin/club-de-programmation/ - ask for session for researchers
- Datascience message : more than tests and software, teach them probabilities (type I error, etc.) and effect size
- [`r-exams`](https://www.r-exams.org/tutorials/elearning/) for Randomized Moodle Exercices, teaching award in 2018 (Social sciences) :
- IDEA DATA SCIENCE DAY 2024 : A student teaching R for students (Take Over)
- Escape game : https://www.unige.ch/innovations-pedagogiques/innovations/escape-game , https://www.unige.ch/innovations-pedagogiques/project-list/escape-game-sur-genially
- The GRAPH courses : https://thegraphcourses.org/
- Scientific computing support : https://www.unige.ch/scicos/ (web dev?)
- TO THINK : When creating a teaching experience (e.g., Take Over), make it reusable for other projects/courses and reproducible !
- IDEA P3 : project, "think about the teacher !" – How a teacher can reuse the other "teaching awards" to enhance the global level of teaching at the university ? It is cool to have awards, it is better when it is reused and embedded in other courses to enhance students' experience
- Matthias Studer, Geneva School of Social Sciences, "Randomized Moodle exercises for quantitative methods courses
- Anastasia Floru, Geneva School of Economics and Management, "Why not learning with fun ? Escape Game an innovative tool to test your skills"

Round Table Empowering Inclusive Data Science Education: Breaking the Psychological Walls :

- Lucia : Learning by doing -> by making mistakes (Natalia : errors are ok, and you can google it)
- The meaning of the data
- Computer teaching : you won't break the computer with the terminal + typing
- IDEA TAKE OVER : Not having fear of a computer anymore / We all know how to read, do you want to know how to use a computer ? Cours sur computer litteracy : 1-2-all : argument why do I fear, then pair, arguments, et dit à tout le monde gather all args
- DISTIC-R&D - look and try to ask a stage

Data Visualisation Workshop :

- Gapminder : présenter données
- [Observablehq](https://observablehq.com/)

# 08.12.2022 - Chandramallika Basak - Brain-Based Mechanisms of Cognitive Enhancemeents in Aing: Benefits of Computerized Training

- Age-related changes in cognition and brain :
	- Declines in :
		- Processing speed, WM, EF, LTM episodic, Gf (Park & Bischoff, 2010)
		- Gray matter volume (GM) in FP cortices, hippocampus (decline more shallo, more unique, may be sign of pre-dimensia)  and cerebellum (Raz N et al., 2005)
		- White matter (WM) (Qin et al., 2016)
- Alzheimer's disease :
	- 48M gloablly
	- characterized by cognitive and behavioral deficits involving some form of permanenet brain damarge
	- AD - most common form dementia (50% of OA over 80 have AD). Progressive, degenerate and fatal
	- Neurological changes in AD :
		- Neurofibrillary tangles, which destroy vital cell transport system made of proteins (Tau)
		- Plaques consisting of a core beta-amyloid, a protein, surrounded by degenerated fragmentets of dyins or dead neurons
		- Rapid death of neurons due to lack of nutrients
	- Compression of morbidity
- How can we improve broad cognitive abilities in older adultes : *cognitive flexbility* (through WM)
- What are the best strategies to offset CA : *strategic optimization* (inter-ind differences)
- Basak, C., Qin, S., & O'Connell, M. A. (2020). Differential effects of cognitive training modules in healthy aging and mild cognitive impairment: A comprehensive meta-analysis of randomized controlled trials.Psychology and Aging, 35(2), 220–249. https://doi.org/10.1037/pag0000442 :
	- No diff bw active and passive control group
	- Effet of cog training in Healthy Adults (HA) : .27, and .28 for Mild Cogntiive Impairment (MCI)
	- For single component training : near trans sig* across reasong, proc speed, EF, epidosic memory (Fig.3)
	- Multi comp had near AND far including VG training (engagement) (Fig. 4)
- Miyake et al., 2000 : switch, inhibition, updating
- Qin, S. & Basak, C. (2020). Age-related differences in brain activations during working memory updating: an fMRI study. Neuropsychologia, 138, 107335. https://doi.org/10.1016/j.neuropsychologia.2020.107335 :
	- Better EF training task for far transfer
- [O'Connell & Basak (2018)](https://www.sciencedirect.com/science/article/pii/S0028393218301544) :
	- Link bw fronto parietal et Default Mode Network
- Basak & Skolasinka :
	- FP : greater d' does not predict RT, but RT less varaible
- Physical activity and brain function during MM :
	- Quin & Basak, 2020, 2022 :
		- Task-switching paradigm : The combined effects of 2 cardiovascular risk factos is greater than effects of 1 risk factor on maladaptive overactivations

# 02.12.2022 - Swiss Reproducibility Network - Preregistration & Registered reports: how to improve the credibility and reproducibility of your research

- [Registered reports](https://cos.io/rr/) :
	- allow the method and the logic of the study to be peer-reviewed before execution
	- intro method data anlysis plan and submit stage 1 (3m) -> revision (2m) -> IPA received & data collection (2m) -> data analysis (3m) -> stage 2 (1m) -> published (3m)
- OSF to prereg + provide templates
- [OSFregistries](https://osf.io/registries) : search engine for prereg
- [aspredicted](https://aspredicted.org/) - prereg around 1-2 weeks to talk about it
- IPA : In-Principle-Acceptance
- VA : Sean because they would "typically exclude these responses" - say in the analysis that they forgot while reporting reasons why to exclude the answers
	- Prereg is not a prison - one can deviate, as long as this is clearly explained in the manuscript
- VB : Mei, as you said earlier, pre-reg does not take more time than a typical reg -
	- Prereg is time-consumming (before data collection/analysis) but increase credibility after
- VC : Bert : prereg is not about the quality of the overall study
	- Prereg does not mean good science and does not solve all issues
- VD : Prereg does not impact curiosity
- VE : Prosper : as long as you tell it in the methods and have prior hypotheses
	- You still have methods and analyses that you can prereg
- VF : Tina, prereg has a timestamp so no worries about being scooped
	- An embargo keeps a prereg pricate until a specified date

# 11.10.2022 - Cvetomir Dimov - An Integrated Model of Collaborative Skill Acquisition: Anticipation,Control Tuning, and Role Adoption

- Space Fortress
- ACT-R ([Anderson, 2007](https://www.amazon.com/Physical-Universe-Oxford-Cognitive-Architectures/dp/0195398955)) unified thepory of the mind
