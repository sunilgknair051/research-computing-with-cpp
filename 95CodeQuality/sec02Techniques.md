# Techniques for Improving Software Quality

## Software quality assurance

Software quality assurance is a **planned and systematic** program of activities designed to ensure that a system has the desired characteristics

It requires to focus on:

- The product itself
- The software-development process 

Some elements of a software-quality program are described in following

## Software-quality objectives

One powerful technique for improving software quality is **setting explicit quality objectives from among the external and internal characteristics**

Without explicit goals, programmers might work to **maximize characteristics different** from the ones you expect them to maximize


## Explicit quality-assurance activity for scientific correctness

One common problem is that **quality is perceived as a secondary goal**

However research insitutions must show programmers that **quality is a priority for obvious scientific validity reasons**

Making the quality-assurance activity explicit makes the priority clear, and programmers will respond accordingly

## Testing strategy 

Execution testing can provide a detailed assessment of a **software reliability**

Developing a test strategy is effective in conjunction with:

- Requirements
- Architecture
- Design

Testing is perceived as the primary method of both

- Quality assessment
- Quality improvement 

This is too heavy a burden for testing to bear by itself

## Software-engineering guidelines 

Guidelines should control the technical character of the software as it’s developed. 

Such guidelines apply to all software development activities, including:

- Problem definition
- Requirements development
- Architecture
- Construction
- System testing

Have a look at **[Code Complete](https://www.amazon.co.uk/s?k=code+complete&adgrpid=52073485806&gclid=CjwKCAiAy9jyBRA6EiwAeclQhNeIeRSvfRPKfkQ3pzGvE9zfmQQ0oiwNCUE4wRDXdLC2lLsLAq8CkxoC3iUQAvD_BwE&hvadid=259049849187&hvdev=c&hvlocphy=1006886&hvnetw=g&hvqmt=e&hvrand=10893684408248939013&hvtargid=aud-857384558340%3Akwd-27623266&hydadcr=28148_1724781&tag=googhydr-21&ref=pd_sl_72sxhqy3xx_e)**, **[Clean Code](https://www.amazon.co.uk/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882/ref=sr_1_2?adgrpid=52073485806&gclid=CjwKCAiAy9jyBRA6EiwAeclQhNeIeRSvfRPKfkQ3pzGvE9zfmQQ0oiwNCUE4wRDXdLC2lLsLAq8CkxoC3iUQAvD_BwE&hvadid=259049849187&hvdev=c&hvlocphy=1006886&hvnetw=g&hvqmt=e&hvrand=10893684408248939013&hvtargid=aud-857384558340%3Akwd-27623266&hydadcr=28148_1724781&keywords=code+complete&qid=1582713508&sr=8-2)** and others 

## Informal technical reviews 

Many software developers review their work before turning it over for formal review

Informal reviews include: 

- Desk-checking the design or the code
- Walking through the code with a few peers (Pair-programming)

## Formal technical reviews 

One part of managing a software-engineering process is catching problems at the _lowest-value_ stage

When the least investment has been made and when problems cost the least to correct 

To achieve such a goal, developers use **_quality gates_** 

Periodic tests or reviews that determine whether the quality of the product at one stage is sufficient to support moving on to the next 

**_Quality gates_** are usually used to transition between requirements development and architecture, architecture and construction, and construction and system testing

For instance: Pull-Request reviews on GitHub
