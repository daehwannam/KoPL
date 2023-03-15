# KoPL: Knowledge-Oriented Reasoning Question Answering Programming Language

[installation](#installation) | [quickstart](#quickstart) | [documentation](#documentation) | [website](#website)

The full name of KoPL is Knowledge oriented Programming Language, which is a programming language designed for complex reasoning questions and answers. We can express the natural language question as a KoPL program composed of basic functions, and the result of the program operation is the answer to the question. Currently, KoPL's 27 basic functions cover operations on various knowledge elements (such as concepts, entities, relationships, attributes, modifiers, etc.), and support queries of multiple question types (such as counting, fact verification, comparison, etc.). KoPL provides a transparent reasoning process for complex problems, which is easy to understand and use. KoPL is oriented to different forms of knowledge resources such as knowledge base and text, and has strong scalability.

The following code demonstrates how to use Python code to implement reasoning question answering for a natural language question.

```python
from kopl.kopl import KoPLEngine
from kopl.test.test_example import example_kb

engine = KoPLEngine(example_kb) # Create an example engine that can operate on the knowledge base example_kb

# Query question: Who is taller, LeBron James Jr. or his father?
ans = engine.SelectBetween( # Among the two entities, query the entity with greater 'height'
   engine.Find('LeBron James Jr.'), # find entity 'LeBron James Jr'
   engine.Relate( # Find 'father' with 'LeBron James Jr'
     engine.Find('LeBron James Jr.'), # find entity 'LeBron James Jr'
     'father', # relationship label
     'forward' # 'forward' represents 'LeBron James Jr' as the head entity
   ),
   'height', # attribute label
   'greater' # query for entities with greater attribute values
)

print(ans) # ans is a list of entity names

```

In this example, we asked who is taller between LeBron James Jr. and his father, and the KoPL program gave the correct answer: LeBron James!

# Install

KoPL supports Linux (e.g., Ubuntu/CentOS), macOS, Windows.

Its dependencies are:

* python >= 3.6

* tqdm >= 4.62


KoPL provides pip installation, and the Ubuntu installation command will be shown below:

```bash
   $ pip install KoPL tqdm
```

run the code below

```python
import kopl

from kopl.test.test_example import *

run_test()
```
If the test runs successfully, congratulations you have successfully installed.

# quick start
You can prepare your own knowledge base and use KoPL to implement reasoning question answering. For the format of the knowledge base, please refer to [Knowledge Base](https://kopl.xlore.cn/doc/4_helloworld.html#id1).
For more simple questions and answers using the KoPL program, please refer to [Simple Questions and Answers](https://kopl.xlore.cn/doc/5_example.html#id2), and for complex questions and answers, please refer to [Complex Questions and Answers](https://kopl.xlore.cn/doc/5_example.html#id8).

You can also use the [Query Service](https://kopl.xlore.cn/queryService) we provide you to quickly start your KoPL journey.

# document
We provide you with KoPL[document](https://kopl.xlore.cn/doc/index.html), which introduces in detail the knowledge elements of KoPL, the basic functions of KoPL, and the API of KoPL engine.

# website
https://kopl.xlore.cn

# Changes from the [original project](https://github.com/THU-KEG/KoPL)
- This forked project is translated into English from Chinese via Google Translate.
- Tab characters used to indent python code are replaced with space characters.
