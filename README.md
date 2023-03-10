# KC-Data-Analyst-intermediate-project
Analysis of the data on e-learning platform

## e-learning project description: variant 2

Product manager Vasily asked to analyze completed lessons and answer the following questions:

**1.** How many students successfully passed only one course? (Successful completion is passing the exam for the course) (7 points).

**2.** Identify the hardest and easiest exams: find the courses and exams within the course that have the lowest and highest completion rates*. (5 points)

**3.** For each subject, determine the average time it takes to pass exams (by passing, we mean the last successful passing of the exam by the student). (5 points)

**4.** Identify the most popular courses (TOP-3) by the number of registrations. Also, courses with the highest churn (TOP-3). (8 points)

**5.** Write a python function that allows for cohort (semester) analysis. From the beginning of 2013 to the end of 2014, identify the semester with the lowest course completion rate and the longest average course completion times. (10 points)

**6.** Often, audience quality analysis uses segmentation approaches. Using python, build adapted RFM clusters of students to qualitatively assess your audience. In the adapted clustering, you can choose the following metrics: R - average time to pass one exam, F - course completion rate, M - average number of points received for the exam. Describe in detail how you created the clusters. For each RFM segment, build boundaries for the metrics of recency, frequency, and monetary for interpreting these clusters. An example of such a description: RFM segment 132 (recency = 1, frequency = 3, monetary = 2) has boundaries for recency metrics from 130 to 500 days, frequency from 0.1 to 0.5, and monetary from 55 to 72 points. The approach description can be found [here](https://medianation.ru/blog/analitika/avtomatizatsiya-rfm-analiza-kak-segmentirovat-klientskuyu-bazu-na-python/). (35 points)

*_completion rate_ = number of successful exams / number of all attempts to pass the exam

**Files:**

- [assessments.csv](https://disk.yandex.ru/d/PBW7aUHGuodFDA) - this file contains information about assessments in the test. Usually each subject in a semester includes a series of tests with grades, followed by a final exam (assessment).

    _code_module_ - subject identification code.

    _code_presentation_ - semester (Identification Code).

    _id_assessment_ - test (assessment identification number).

    _assessment_type_ - type of test. There are three types of assessment: teacher assessment (TMA), computer assessment (CMA), course exam (Exam).

    _date_ - information about the final test submission date. Calculated as the number of days since the start of the semester. The start date of the semester is numbered 0 (zero).

    _weight_ - the weight of the test as a percentage of the course grade. Usually exams are considered separately and have a weight of 100%; the sum of all other grades is 100%.

- [courses.csv](https://disk.yandex.ru/d/m0Z6QYNT46f9tQ) - the file contains a list of courses by semesters.

    _code_module_ - subject (identification code).

    _code_presentation_ - semester (identification code).

    _module_presentation_length_ - semester duration in days.

- [studentAssessment.csv](https://disk.yandex.ru/d/lsmdbYB0iM7p3w) - this file contains the results of students' tests. If a student does not submit a work for assessment, the result is not recorded in the table.

    _id_assessment_ - test (identification number).

    _id_student_ - student identification number.

    _date_submitted_ - date the student submitted the test, measured as the number of days since the start of the semester.

    _is_banked_ - the fact of transferring a test from the previous semester (sometimes courses are re-credited to students who have returned from academic leave).

    _score_ - the student's grade on this test. The range is from 0 to 100. A score below 40 is an unsuccessful test.

- [studentRegistration.csv](https://disk.yandex.ru/d/Yse4Y6RJqg_WaA) - this file contains information about when a student registered to take a course in a semester.

    _code_module_ - subject (identification code).

    _code_presentation_ - semester (identification code)

    _id_student_ - student identification number.

    _date_registration_ - date of student registration. This is the number of days measured from the start of the semester (for example, a negative value of -30 means that the student registered for the course 30 days before it started).

    _date_unregistration_ - date of cancellation of the student's registration for the subject. For students who have completed the course, this field remains blank.
