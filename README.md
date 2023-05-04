# CS182 FP

Our final project for CS182 Spring 2023 is to create a NanoGPT HW Problem Set.
This final project includes Jupyter notebook full of instructions and tutorials for students to complete the problem set, and an autograder solution for grading.

This repo contains:
- `nanogpt.ipnyb`: Jupyter notebook for students
- `nanogpt_sol.ipnyb`: Jupyter notebook solutions
- `data`: Dataset file
- `grader`: Sanity checks for students
- `grader_internal`: Hidden autograder tests

Note that the GitHub repository for **students** is in a separate repository that does not contain `grader_internal` and `nanogpt_sol.ipnyb` files. Repo link: https://github.com/KevinLiu819/CS182_FP_Student

## Grading

The code below can be used for grading. The end of the `nanogpt_sol.ipnyb` also contains code to internally grade students' homework submissions.

```python
from grader_internal import Autograder
import numpy as np

grader = Autograder()
grade = grader.grade(np.load("submission.npz"))
grade_percent = sum(grade) / 10. * 100
print(f"Grade: {sum(grade)}/10.0") # Regular format
print("Grade: %.2f%%" % (grade_percent)) # Rounded percentage format
```