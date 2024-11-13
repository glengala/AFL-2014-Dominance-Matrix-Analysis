# AFL-2014-Dominance-Matrix-Analysis
### Project Overview
This project analyzes AFL match data from the 2014 season to predict team rankings using dominance matrices, a mathematical approach for ranking when not all teams have played each other. The goal is to evaluate if the dominance matrix method can reliably forecast final standings based on partial season data.

### Objectives
- Test the effectiveness of the dominance matrix method by comparing its predictions to the actual AFL ladder at various points in the season.
- Experiment with different dominance matrix configurations to determine which provides the most accurate ranking.
- Assess the reliability of the dominance matrix method for predicting end-of-season standings.
### Data Processing
- Data Extraction: Transformed the 2014 AFL match data from PDF format into an Excel-friendly format, separating key details such as team names, scores, and round information for easier analysis.
- Score Transformation: Extracted the scores into separate columns for the Home and Away teams, enabling calculations such as win-loss ratios and dominance scores.
- Played Twice Match Handling: Identified instances where teams played each other twice and applied specific rules to handle these cases:
  - Average Calculation: For teams that played twice, calculated the average score for each team across both games.
  - Single Encounter Calculation: For teams that played only once within the chosen rounds, used the score directly.
- Dominance Matrix Creation: Constructed an 18x18 dominance matrix (D(m)) for selected rounds (e.g., D(13), D(16), D(19), D(22)), representing team performance up to each respective round.
  - Formulas and Conditions: If a team played twice within the round, scores were averaged; if there was no match (indicated by a blank), a sum of prior data was used for D(m) based on team names.
- Manual Adjustments Due to Excel Limitations: Due to limitations with Excel functions, rounds were manually deleted to isolate D(13, 16, 19, 22). The computed values were then copied as static values into the r1 matrix for accurate ranking calculations. The full dataset is retained at the end of the Excel sheet.
### Methodology
- Ranking Calculations: For each matrix, calculated first-order rankings (r1) based on initial dominance values, second-order rankings (r2) and third-order rankings (r3) which predicted ranking for teams that have not been played yet by looking at the played games around them
- Weight Adjustments: Experimented with different weight combinations for r1, r2, and r3 to evaluate the impact on prediction accuracy.
- Formula Optimization: Tested multiple formula configurations by adjusting weights across r1, r2, and r3 to identify the most accurate prediction model for end-of-season rankings.
- Comparison to Actual Standings: The final weighted rankings were compared to the AFL ladder to determine the accuracy of each formula variation, helping to conclude the most effective weighting approach.

### Results
Key findings showed that the dominance matrix method provides a reasonably accurate prediction of team rankings after a certain number of rounds. Results indicate that accuracy improves as more games are played, though some inconsistencies exist when teams have not played each other often enough.
![image](https://github.com/user-attachments/assets/60f0f352-5153-44bc-a5ee-edc7a0e7c646)


Conclusion
Relying solely on dominance matrices to predict team rankings early in the season is insufficient. Other factors, such as injuries, strategic changes, and individual team member performance, must also be considered. However, Dominance matrices provide a good overall indicator of team strength.



