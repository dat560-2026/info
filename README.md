# DAT560 Generative AI

- [Course Structure](#Structure)
- [Lecture Schedule](#Schedule)
- Labs
   - [Signup](signup.md)
   - [Submission](submission.md)
- [Updates](#Updates)
- Communication
   - [Discord server](https://github.com/dat240-2025/info/blob/main/signup.md#discord-dat560-server-registration)
   - [Discord server invite](https://discord.gg/Wc6AqbAqE5)
   

# Structure
- Lectures:
   - The lectures are on Wednesdays (KE E-101) and Fridays (KE A-101) (from 10.15 to 12.00) only in-person in (see the full schedule [here](https://tp.educloud.no/uis/app/schedule?semester=26v&scheduleType=course&filterOpen=true&summary=true&pastWeeks=false&tab=calendar&course=DAT560%C2%A41))
   - The lecturers are Vinay Setty and Petra Galuscakova.
- Labs:
   - The labs are in-person on Wednesdays (12.15 - 14.00) in KE D-302.
   - Gabriel Iturra-Bocaz is the teaching assistant for the course.
   - Make an appointment with the teaching assistant for the help with lab.
   - 3 ungraded (pass/fail) mandatory assignments for qualification to final exam.
- Project:
   - 40% of the final grade is assigned to the group project (working code + written report + presentation).
   - 60% of the final grade is based on a written exam on Inspera with no Internet connection.

# Schedule

(Lab submission deadlines are marked with **bold**.)

| Week | Date       | Topic                               | Lecturer | Resources                      | Comments |
|------|------------|--------------------------------------|----------|--------------------------------|----------|
| 2    | 07.01.2026 | Introduction (What is generative AI) | VS       | Generative Deep Learning Ch. 1 |          |
|      |            | – Course structure                   |          |   [slides](slides/Lecture-01a-Introduction.pdf)                             |          |
|      |            | – Assignments / project             |          |                               |          |
|      |            | – Probability and Statistics basics            |         |    [slides](slides/Lecture-01c-probability_theory.pdf)                             |          |
|      |            | – Generative modeling                |          |   [slides](slides/Lecture-01b-generative_modeling.pdf)                             |          |
|      | 07.01.2026 | Lab                                  | GIB      |                                |          |
|      |            | – Setup Python / VS Code             |          |                                |          |
|      |            | – Setup QuickFeed                    |          |                                |          |
|      | 09.01.2026 | Deep learning recap                 | PG       | Generative Deep Learning Ch. 2 | VS away  |
|      |            | – Deep neural networks              |          |   [slides](slides/Lecture-02a-DL.pdf) [notebook](https://colab.research.google.com/drive/1BMxHC7E3X2BIbZRn9FGdR3H4_K0EJNbZ?usp=sharing)                             |          |
|      |            | – CNN                               |          |    [slides](slides/Lecture-02b-CNN.pdf) [notebook](https://colab.research.google.com/drive/1U3t4qWZSX6E43TJ37hJE_aeCt3t2puyS?usp=sharing)                           |          |
| 3    | 14.01.2026 | Variational Autoencoders            | VS       | Generative Deep Learning Ch. 3 |          |
|      |            | – Autoencoders                      |          |                                |          |
|      |            | – VAE                               |          |                                |          |
|      | 14.01.2026 | Lab                                  | GIB      |                                |          |
|      | 16.01.2026 | VAE continued                       | VS       | Generative Deep Learning Ch. 3 |          |
| 4    | 21.01.2026 | GAN 1                               | VS       | Generative Deep Learning Ch. 4 |          |
|      | 22.01.2026 | Lab                                  | GIB      |                                |          |
|      | 23.01.2026 | GAN 2                               | VS       | Generative Deep Learning Ch. 4 |          |
| 5    | 28.01.2026 | Language Models – part 1            | VS       |                                |          |
|      | 28.01.2026 | **Assignment 1 deadline**               |          |                                |          |
|      | 29.01.2026 | Lab                                  | GIB      |                                |          |
|      | 30.01.2026 | Language Models – part 2            | VS       |                                |          |
| 6    | 04.02.2026 | LLM foundations – part 1            | VS       |                                |          |
|      | 05.02.2026 | Lab                                  | GIB      |                                |          |
|      | 06.02.2026 | LLM foundations – part 2            | VS       |                                |          |
| 7    | 11.02.2026 | LLM prompting                       | VS       |                                |          |
|      |            | Vision models                       |          |                                |          |
|      | 11.02.2026 |                |          |                                |          |
|      | 12.02.2026 | Lab                                  | GIB      |                                |          |
|      | 13.02.2026 | LLM fine-tuning                     | VS       |                                |          |
|      |            |                           |          |                                |          |
| 8    | 18.02.2026 |           | VS       |                                |          |
|      | 19.02.2026 | **Assignment 2 deadline**                                  | GIB      |                                |          |
|      | 20.02.2026 |          | VS       |                                |          |
| 9    | 25.02.2026 |                                      |          |                                |          |
|      | 26.02.2026 |               | GIB      |                                |          |
|      | 27.02.2026 |                                      |          |                                |          |
| 10   | 04.03.2026 |                                      |          |                                |          |
|      | 05.03.2026 | Lab                                  | GIB      |                                |          |
|      | 06.03.2026 |                                      |          |                                |          |
| 11   | 11.03.2026 |                                      |          |                                |          |
|      | 12.03.2026 | **Assignment 3 deadline**                                   | GIB      |                                |          |
|      | 13.03.2026 |                                      |          |                                |          |
| 12   | 18.03.2026 |                                      |          |                                |          |
|      | 19.03.2026 | Lab                                  | GIB      |                                |          |
|      | 20.03.2026 |                                      |          |                                |          |
| 13   | 25.03.2026 |                                      |          |                                |          |
|      | 26.03.2026 | Lab                                  | GIB      |                                |          |
|      | 27.03.2026 |                                      |          |                                |          |
| 14   | 01.04.2026 | No lecture easter week                                     |          |                                |          |
|      | 03.04.2026 | No lecture easter week                                     |          |                                |          |
|      | 02.04.2026 | No lecture easter week                                  | GIB      |                                |          |
| 15   | 08.04.2026 |                                      |          |                                |          |
|      | 10.04.2026 |                                      |          |                                |          |
|      | 09.04.2026 | Lab                                  | GIB      |                                |          |
| 16   | 15.04.2026 |                                      |          |                                |          |
|      | 17.04.2026 | **Project + report due**                                     |          |                                |          |
|      | 16.04.2026 | Lab                                  |       |                                |          |
| 17   | 22.04.2026 |                                      |          |                                |          |
|      | 23.04.2026 | Project presentation + Q&A                                  |       |                                |          |
|      | 24.04.2026 |  Project presentation + Q&A                                    |          |                                |          |

