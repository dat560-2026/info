# DAT560 Generative AI

- [Course Structure](#Structure)
- [Lecture Schedule](#Schedule)
- Labs
   - [Signup](signup.md)
   - [Assignment 1](assignments/assignment1.md)
- [Updates](#Updates)
- Communication
   - [Discord server](https://github.com/dat240-2025/info/blob/main/signup.md#discord-dat560-server-registration)
   - [Discord server invite](https://discord.gg/Wc6AqbAqE5)

# Updates
- Assignment 1 is now released, you should have received GitHub org invite and link to the assignment in Canvas. See this [guide](assignments/assignment1.md) to get started and for useful tips.

# Structure
- Lectures:
   - The lectures are on Wednesdays (KE E-101) and Fridays (KE A-101) (from 10.15 to 12.00) only in-person in (see the full schedule [here](https://tp.educloud.no/uis/app/schedule?semester=26v&scheduleType=course&filterOpen=true&summary=true&pastWeeks=false&tab=calendar&course=DAT560%C2%A41))
   - The lecturers are [Vinay Setty](https://vinaysetty.com) and [Petra Galuscakova](https://galuscakova.github.io/).
- Labs:
   - The labs are in-person on Wednesdays (12.15 - 14.00) in KE D-302.
   - [Gabriel Iturra-Bocaz](https://giturra.cl/) is the teaching assistant for the course.
   - Make an appointment with the teaching assistant for the help with lab.
   - 3 ungraded (pass/fail) mandatory assignments for qualification to final exam.
   - Each assignment must be submitted to GitHub Classroom platform and achieve at least 80% score in the tests and evaluations to be approved.
   - Once 80% score is reached the student must get the assignment approved by one of the TAs or lecturers. This approval process is intentionally manual to ensure that you understand assignment submission you made and be prepared to answer any questions about it.
   - Approval can be done after the deadline also but better to get it done sooner.
   - Everyone has 5 slip days which you are free to spend as you wish (on any of the three assignments).
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
|      |            |                    |          |                                |          |
|      | 09.01.2026 | Deep learning recap                 | PG       | Generative Deep Learning Ch. 2 | VS away  |
|      |            | – Deep neural networks              |          |   [slides](slides/Lecture-02a-DL.pdf) [notebook](https://colab.research.google.com/drive/1BMxHC7E3X2BIbZRn9FGdR3H4_K0EJNbZ?usp=sharing)                             |          |
|      |            | – CNN                               |          |    [slides](slides/Lecture-02b-CNN.pdf) [notebook](https://colab.research.google.com/drive/1U3t4qWZSX6E43TJ37hJE_aeCt3t2puyS?usp=sharing)                           |          |
| 3    | 14.01.2026 | Variational Autoencoders            | VS       | Generative Deep Learning Ch. 3 |          |
|      |            | – Autoencoders                      |          |  [slides](slides/Lecture-03-VAE.pdf)                              |          |
|      |            | – VAE                               |          |                                |          |
|      | 14.01.2026 | Lab                                  | GIB      |                                |          |
|      | 16.01.2026 | VAE continued                       | VS       | Generative Deep Learning Ch. 3 |          |
| 4    | 21.01.2026 | GAN 1                               | VS       | Generative Deep Learning Ch. 4 |          |
|     |  | Why study GANs? and comparision to VAE                               | VS       | [slides](slides/Lecture-04-GANs.pdf) |          |
|     |  | How to train GANs?                               | VS       |  |          |
|     |  | GAN failures                               | VS       |  |          |
|     |  | GAN vairations (WGAN and CGAN)                               | VS       |  |          |
|      | 21.01.2026 | Lab                                  | GIB      |                                |          |
|      | 23.01.2026 | GAN 2                               | VS       | Generative Deep Learning Ch. 10 |          |
|     |  | Advanced GANs                               | VS       |  |          |
|     |  | ProGAN                               | VS       |  |          |
|     |  | StyleGAN                               | VS       |  |          |
| 5    | 28.01.2026 | Language Models – part 1            | VS       |                                |          |
|      | 28.01.2026 | **Assignment 1 deadline**               |          |                                |          |
|      | 29.01.2026 | Language Models – part 2            | VS      |                                |          |
| 6    | 04.02.2026 | **No lecture**           | Department workshop       |                                |          |
|      | 04.02.2026 | Lab                                  | GIB      |                                |          |
|      | 06.02.2026 | LLM foundations – part 1            | VS       |                                |          |
| 7    | 11.02.2026 | LLM foundations – part 2                       | VS       |                                |          |
|      | 11.02.2026 |  Lab              |          |       GIB                         |          |
|      | 13.02.2026 |  LLM prompting                     | VS       |                                |          |
| 8    | 18.02.2026 |  LLM fine-tuning - part 1        | VS       |                                |          |
|      | 18.02.2026 | **Assignment 2 deadline**                                  | GIB      |                                |          |
|      | 20.02.2026 |  LLM fine-tuning - part 2        | VS       |                                |          |
| 9    | 25.02.2026 |  LLM Applications (tentative)                                    |    VS      |                                |          |
|      | 25.02.2026 |               | GIB      |                                |          |
|      | 27.02.2026 |  Multilingual Language Models        | PG         |                                |          |
| 10   | 04.03.2026 |  Mulitmodal Models - part 1          | PG         |                                |          |
|      | 04.03.2026 | Lab                                  | GIB      |                                |          |
|      | 06.03.2026 |  Mulitmodal Models - part 2          | PG       |                                |          |
| 11   | 11.03.2026 |  Music and Voice                     | PG       |                                |          |
|      | 11.03.2026 | **Assignment 3 deadline**            | GIB      |                                |          |
|      | 13.03.2026 |  Knowledge and RAG                   | PG       |                                |          |
| 12   | 18.03.2026 |  Agentic generative AI               | PG       |                                |          |
|      | 18.03.2026 | Lab                                  | GIB      |                                |          |
|      | 20.03.2026 |  World models                        | PG       |                                |          |
| 13   | 25.03.2026 |  Evaluation of Generative Systems    | PG       |                                |          |
|      | 25.03.2026 | Lab                                  | GIB      |                                |          |
|      | 27.03.2026 |  Ethics and responsible AI, fairness and bias, alignment | PG         |                                |          |
| 14   | 01.04.2026 | No lecture easter week                                     |          |                                |          |
|      | 01.04.2026 | No lecture easter week                                     |          |                                |          |
|      | 03.04.2026 | No lecture easter week                                  | GIB      |                                |          |
| 15   | 08.04.2026 | Invited talk                         | TBD      |                                |          |
|      | 08.04.2026 | Lab                                  | GIB      |                                |          |
|      | 10.04.2026 | Invited talk                         | TBD      |                                |          |
| 16   | 15.04.2026 | Lab                                  |          |                                |          |
|      | 15.04.2026 | **Project + report due**                                     |          |                                |          |
|      | 17.04.2026 | Lab                                  |       |                                |          |
| 17   | 22.04.2026 | Project presentation + Q&A                                      |          |                                |          |
|      | 22.04.2026 | Project presentation + Q&A                                  |       |                                |          |
|      | 24.04.2026 |  Project presentation + Q&A                                    |          |                                |          |

