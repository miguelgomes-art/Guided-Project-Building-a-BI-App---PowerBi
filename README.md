# Guided-Project-Building-a-BI-App

Courses are the most important part of Dataquest's business. Having high-quality, effective, and engaging courses is a top company priority. As the course catalog grows, it becomes more difficult to rely purely on qualitative data. In order to help Dataquest decide which courses need improvement, we're going to build a Power BI app that surfaces quantative data on course quality.

We'll start this guided project by importing data in Power BI and building out the data model. Then we'll create series of analyses and visualizations on course completion rates and course ratings. Based on these analyses, we'll make a recommendation for which courses should be improved. Lastly, we'll publish the report to a Power BI app.

## Importing and Exploring the Data
This project has three data tables, stored as CSVs.

### Mission Progress Data
missionprogress_id — a unique ID for the user and the lesson
started_at — the date and time the learner started the lesson
lession_id — a unique ID for a lesson
is_complete — a Boolean (True/False) for whether the learner completed the lesson
completed_at — the date and time when the learner completed the lesson

### NPS Survey Data
response_id — a unique ID for the NPS survey response
date — the date when the learner submitted their survey response
score — the learner's response to the question "On a scale of 1-10, how likely are you to recommend Dataquest to someone interested in learning data skills?"

### Lesson and Course Structure Data
lesson_id — a unique ID for a lesson
course_id — a unique ID for a course

### Instructions
1. Import the following datasets into Power BI Desktop:

    lesson_progress.csv
    nps_data.csv
    course_lessons.csv
## Create the Data Model
Before starting the analysis, we need to create the data model. Creating the data model requires making the relationships between the datasets so they can be used together. We may need to make adjustments to the data model as we work through the analysis, but for now, we can join the tables using common fields.

### Instructions
1. Change the data types for the lesson_id and course_id fields to text.

  Do this for all tables where these fields exist.
2.Create relationships between lesson_id in the course_lesson table and lesson_id in the other two tables.

## Lesson Completion Rate
The first analysis we'll work on uses the lesson completion data. Lesson completion rate is a useful metric for understanding course quality. Lessons with high completion rates show that learners understand the curriculum and are engaged enough to complete the lesson. Low completion rates suggest there may be an issue that needs to be addressed.

As you complete this project, you may need to use DAX functions that you're unfamiliar with. Being able to quickly search for, learn, and use a new function for a DAX is a critical skill for analysts.

### Instructions
1. Let's start by creating a KPI visual that shows the current completion rate across all lessons. Create a completion rate measure by dividing the number of completed lessons (rows where is_complete = True) by total lessons started (all rows).

  You can do this with the COUNTROWS function.
  Create a new column named month_year that takes just the month and year from started_at. Use that column for the trend axis. If you just use the started_at field, it will aggregate the data by calendar month, which isn't what we want.
2. Add another measure and associated KPI visual that shows the number of lesson completions by month_year.

3. Build a line chart of completion rate by month.

4. Create a scatterplot that shows the number of lessons started on the x-axis and completion_rate on the y-axis.

5.Add a Slicer with course_id so dashboard users can filter the data for a specific course or set of courses.

6. Optional challenge: Create a histogram of completion_rate.

  This requires adjusting the data model to create a new table that shows lesson completion by lesson_id.

## Net Promoter Score - NPS

### Calculating Net Promoter Score

Net promoter score (NPS) is a common metric used across industries to measure customer satisfaction. You can read more about it here. The resulting metric gives you a number between -100 and 100. It's calculated from the results of a survey question that asks "On a scale of 1-10, how likely are you to recommend this product to others?"

To calculate NPS, you split the scores into three groups:

  Promoters (response of 9 or 10) — These learners are enthusiastic about their experience and likely to refer it to others.

  Passives (response of 7 or 8) — These learners are satisfied about their experience, but they're not quite loyal customers yet.

  Detractors (response of 1-6) — These learners are unsatisfied and less likely to continue learning with Dataquest.

To get the final NPS score, you take the number of promoters, subtract the number of detractors, divide the difference by the total number of responses, then multiple it by 100.

### Dataquest NPS Report

Dataquest students receive periodic NPS surveys, and the results are used to measure lesson and course quality. In this step, you'll create a new page in your report that shows various visualizations of NPS data.

### Instructions
1. Create a new page in your report, and add the following visuals to it.

2. Add KPI visuals for the NPS score and the number of survey responses by month. As in the previous step, create a new month_year variable to use for the trend axis.

3. Build a line chart of NPS score by month.

4. Create a scatter plot of the number of survey responses (x-axis) and NPS (y-axis) by course.

  Set the x-axis to show the data on the logarithmic scale. This will make the plot more readable.

5.Add a histogram of the score from the survey responses. This is the raw score (1-10), not the calculated NPS.

6. Add a Slicer with course_id so dashboard users can filter the data for a specific course or set of courses.

## Make a Recommendation
The value of data analysis in organizations is to help people make decisions. We've done the analysis, now it's time to make a recommendation. Dataquest is trying to make a decision about which of its many courses it should spend time improving. Your responsibility is to provide a recommendation, backed by data, for which five courses they should improve.

### Instructions
1. Create a new page in your report called "Recommendation," and move it to be the first page in the report.

2. Add a text box that explains your recommendation for the five courses that Dataquest should improve. Note that the solution we provide does not include a recommendation. This is to encourage you to come to your own conclusions.

3. Add a table that provides as much detail as possible about the recommended courses, including the completion rate, NPS score, and the number of responses. Use a filter or a group to only include the recommended courses.

4. Add a Q&A visual to all report users to query the data from the recommendation page.
