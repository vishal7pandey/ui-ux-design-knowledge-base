Transcript


Search in video
0:00
Hi everyone, welcome to the session.
0:02
Agentic AI is a rapidly evolving space
0:05
and it will fundamentally reshape how we
0:07
work across processes, team dynamics and
0:09
entire industries. I'm Romeshalla joined
0:13
by my colleague Praep Sridtheran. We are
0:15
both solutions architects working at AWS
0:18
and in this session we will learn more
0:20
about the foundational design patterns
0:22
for agentic AI systems.
0:25
Let's start by understanding what
0:27
agentic AI means and where does it fit
0:29
in the generative AI landscape.
0:33
The evolution of generative AI has
0:35
followed a clear progression with each
0:37
phase bringing new priorities and
0:39
challenges for businesses. In the past,
0:42
AI models used to be trained on specific
0:44
data sets to solve specific problems.
0:47
That required a lot more human oversight
0:50
to see if the AI was getting it right.
0:52
As we continue to evolve towards a fully
0:55
realized agentic world, intelligent
0:57
multi- aent systems will make complex
1:00
decisions and coordinate effortlessly
1:02
with less human oversight, completely
1:05
transforming the way we work and
1:06
innovate.
1:09
AI agents are autonomous software
1:12
systems that have the ability to think
1:14
iteratively, to evaluate results, adjust
1:17
their approach, and continue working
1:19
towards a defined goal. They don't just
1:21
answer questions. They solve problems
1:24
through a process of exploration and
1:26
refinement.
1:30
At its core, agentic AI refers to AI
1:33
systems leveraging distributed
1:35
intelligent agents that not only act
1:37
independently but also collaborate to
1:40
solve highly complex real world
1:42
problems. Agentic AI workflows represent
1:45
a significant leap forward and a
1:48
paradigm shift in AI systems design with
1:50
features including autonomy,
1:52
adaptability, and decision making.
1:57
At the core of agentic AI workflows are
1:59
key design patterns that enable large
2:02
language models to exhibit more
2:04
autonomous and intelligent behavior.
2:08
These key design patterns are
2:10
reflection, tool use, planning, and
2:13
multi-agent.
2:14
Reflection enhances AI's ability to
2:17
evaluate and improve its own outputs.
2:19
Through this, AI can provide more
2:21
accurate and reliable results. The tool
2:24
use pattern enables AI to expand its
2:27
capabilities by utilizing external tools
2:29
and resources.
2:32
Planning pattern is particularly useful
2:34
for managing long-term projects and
2:36
solving complex problems. In multi- aent
2:39
pattern, multiple AI agents collaborate
2:42
to perform complex tasks. Each agent
2:45
takes on specific roles to contribute to
2:47
achieving the overall objective.
2:50
Let's now dive deeper into each of these
2:52
design patterns.
2:55
Reflection is a technique where AI
2:57
models self-evaluate and refine their
3:00
own outputs. This pattern enables AI
3:03
models to become more autonomous,
3:05
creative, and reliable by mimicking
3:07
human-like feedback and revision loops.
3:10
It is particularly useful for large
3:12
language models, allowing them to catch
3:14
mistakes, clarify ambiguities, and
3:17
improve over multiple iterations.
3:20
This pattern involves generation where
3:23
the AI model generates an initial
3:25
response to a given prompt or task.
3:27
Self-reflection where the model
3:30
scrutinizes its output identifying
3:32
potential errors, inconsistencies or
3:34
areas for improvement.
3:38
Iterative refinement where based on the
3:40
self assessment, the model iteratively
3:42
refineses its output making adjustments
3:45
to enhance its quality and accuracy.
3:51
Let's look at an example implementation
3:53
of the reflection pattern using Amazon
3:55
Bedrock. Amazon Bedrock is a fully
3:58
managed service that offers a choice of
4:00
high-erforming foundation models, making
4:02
it easy to build and scale generative AI
4:05
applications. In this architecture
4:07
diagram, you can see the two core steps
4:09
of the reflection pattern, initial
4:12
generation and self-evaluation. The
4:14
first AI model solves the initial
4:16
problem and provides the output and the
4:18
second AI model validates the solution
4:21
demonstrating how AI can self-evaluate
4:23
its results.
4:27
Moving on to the tool use pattern. This
4:29
pattern enables large language models to
4:32
transcend their natural limitations by
4:34
interacting with external functions to
4:36
gather information, perform actions, or
4:39
manipulate data through tool use. Large
4:42
language models are not just confined to
4:44
producing text responses from their
4:46
pre-trained knowledge. They can now
4:48
access external sources and functions to
4:51
gather latest information, process data
4:54
or update systems. The diagram depicts a
4:57
conceptual agentic AI tool use pattern
4:59
where AI system uses multiple
5:01
specialized tools to process user
5:03
queries by accessing various information
5:06
sources.
5:09
Let's look at an example implementation
5:11
of the tool use pattern using Amazon
5:13
Bedrock. In this architecture diagram,
5:16
the tool use pattern enables fetching
5:18
data from various internal and external
5:20
sources and enables real-time lookup of
5:23
contextual information to solve complex
5:25
and realistic problems.
5:28
Thanks. I'll now hand it over to Praep
5:30
to continue diving into the remaining
5:32
design patterns. Hello all, my name is
5:34
Praep Sridan, senior solutions architect
5:36
at AWS and today I'll continue from
5:39
Romesh on the next two foundational AI
5:41
patterns. The pattern number three is
5:44
called planning pattern.
5:47
Now planning pattern is an approach that
5:49
allows large language models to break
5:52
down complex multi-step task into
5:54
smaller manageable chunks instead of
5:57
attacking the problem randomly.
5:59
The LM first creates a structured road
6:02
map and then efficiently executes
6:05
the road map adapting as it emerges. To
6:08
give an example, this would be like when
6:10
coding the LLM would create the overall
6:14
structure of the final result instead of
6:17
writing individual functions. This
6:20
method ensures clarity, prevents
6:21
confusion and keeps the system focused
6:23
on the broader goal through execution.
6:25
We can systematically think of planning
6:27
as four steps. The first step is task
6:30
decomposition. In task decomposition,
6:32
the LLM takes a task and breaks down
6:34
into manageable subtasks. And once this
6:36
is done, then we do what is called a
6:38
strategic structuring where
6:40
systematically organizes steps for goal
6:42
achievement. Then efficient execution
6:45
executes a task and monitors the
6:48
progress and flexible adjustments
6:51
and modifies and adapts plans as needed.
6:53
So by breaking large tasks into smaller
6:57
task the able to provide more clarity
7:00
and stay focused on the broader goal
7:02
instead of getting mired into details.
7:05
This is another view of the same
7:07
pattern. So would first generate task
7:09
and then execute to through tool use
7:11
methodology then compile and provide the
7:13
results back. Let's look at the multi-
7:16
aent collaboration.
7:18
Now this is a fairly popular and well
7:20
understood pattern now but it's also
7:22
probably one of the most powerful
7:23
patterns available. The idea with MAC
7:25
pattern or multi-agent collaboration
7:26
pattern is to build the concept of
7:29
delegation. You can within an
7:31
organization build specialized agents.
7:33
For example, as mentioned here, you can
7:36
build a new modage agent and a mortgage
7:38
domain knowledge base and have a
7:41
supervisor agent then delegate some of
7:43
the tasks to this sub agents and then
7:46
get the task executed. The sub agents
7:49
can operate independently but also
7:51
communicate with each other to
7:52
collaborate to achieve a unified goal.
7:55
This pattern is especially powerful for
7:57
complex use cases requiring diverse
8:00
expertise, parallel processing,
8:02
brainstorming such as research projects.
8:04
There are several types of multi-agent
8:06
patterns, right? There are collaborative
8:08
agents. Each agents work on different
8:10
task as part of sharing progress towards
8:12
unified results. Supervised agents. A
8:15
central supervisor manages and
8:17
coordinates the agents verifying the
8:19
outputs and supervisor tool calling.
8:22
Here the supervisory agent uses LLM
8:24
power tools deciding which agent to call
8:27
and what argument to pass. So there are
8:30
quite a few hybrid models available with
8:33
multi- aent collaboration but generally
8:36
speaking you know when you start
8:38
constructing an agent you want to kind
8:40
of think in terms of a coarse grain
8:42
micros service right and look at carve
8:44
out individual functionality that could
8:47
be a standalone agent and then see how
8:49
you can delegate it across by using a
8:51
supervisor agent. If you look at some of
8:53
the steps involved, we can talk about
8:55
task division which is essentially the
8:56
supervisor agent takes care of
8:58
decomposing the complex problem into
8:59
smaller task and then specialization. It
9:02
identifies which agent to call for the
9:04
particular task. Collaboration agents
9:07
can exchange information and share
9:08
results and this can happen in federally
9:10
among the agents or through the
9:12
supervisor and the supervisor can then
9:14
combine the results to provide the final
9:16
output to the user. And this is another
9:17
view. You can have a finance analyzer
9:20
agent a portfolio architect. And this
9:22
one shows more like a collaboration
9:24
pattern more than a supervised pattern
9:26
because all of them are at the same
9:28
level. But you get the idea having
9:30
multi- aents kind of collaborating and
9:32
providing a useful result to the end
9:34
user.
9:36
As we are building applications with
9:38
generative AI, it's important to follow
9:40
patterns because pattern gives you a
9:43
foundational element and then how we can
9:45
reuse. Thanks for listening to this
9:47
video. Have a good day.