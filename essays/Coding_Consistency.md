---
layout: essay
type: essay
title: "Coding Consistency: The Power of Standards"
date: 2024-02-02
published: false
labels:
  - Coding Standards
  - ESLint
  - IntelliJ
  - Learning
---


## Etiquette in Education

Many of us have always heard the expression, “there are no dumb questions”, as it demonstrates that seeking knowledge includes failure and in order to know, you must learn. So, is there truly such a thing as a dumb question? Yes, yes there is. It’s what I refer to as “ignorant questioning”. This type of question arises when the individual asking it merely wants an answer without actually learning or understanding the problem and its solution. On the other side of this we have smart questions, where someone is explicit about their question, poses possible causes to their problem, and genuinely demonstrates a willingness to learn and merely seeks a little guidance with the issue they’re encountering. This dynamic is widely seen through the realm of tech and programming forums, where on one hand you’ll have say a student trying to get a homework problem solved for them, and on the other someone having some questions regarding a project they’ve been putting a lot of time into, and is merely seeking peer assistance and brainstorming. Smart questions are especially key in fields such as software engineering, where depending on how you formulate your question, could either help you with your problem, or lead to a million different responses that lead nowhere or don’t help you whatsoever. Asking the right questions can not only improve your preexisting knowledge, but also provide deeper insight on both present and future projects that you may be working on. It is important for software engineers to “State what Matters And Research the Topic”.

<img width="250px" 
     class="rounded float-start pe-4" 
     src="../img/questioning/questioning1.png" >

## IntelliJ Impressions

To provide a better perspective on what qualifies as a smart question and a stupid question with a technical context, here are two real questions asked on Stack Overflow, with one being deemed a smart question and the other a dumb one. Let’s see if you can tell which is which. The first question has a user asking, “[Why should I always enable compiler warnings?](https://stackoverflow.com/questions/57842756/why-should-i-always-enable-compiler-warnings/57848116#57848116)”. The description reads, “I often hear that when compiling C and C++ programs I should "always enable compiler warnings". Why is this necessary? How do I do that? Sometimes I also hear that I should "treat warnings as errors". Should I? How do I do that?”. The posting of the question only has this text, and does not include any images or code to go along with it. The user asks mainly general, open-ended questions that lead to very wide-ranging answers from other users. 
Now, let’s take a look at the second question. The second question comes from a user who asks, “[Why is processing an unsorted array the same speed as processing a sorted array with modern x86-64 clang?](https://stackoverflow.com/questions/66521344/why-is-processing-an-unsorted-array-the-same-speed-as-processing-a-sorted-array)”. The user first states that this question comes from an old question the user saw on the forums and his curiosity to test and understand it.They explain that they are operating with AMD Ryzen 9 5950X, clang++ 10 and Linux, and then provide code from the original question. The user then explains what they are noticing, asks another question off of that, showing different runs of the code, and then at the end provides an update to the post.
If you couldn't already guess, the first question is what we would refer to as a stupid question. Now, that’s not to say that this person is somehow intentionally being ignorant or doesn’t know enough about the topic. The question itself is not necessarily a stupid one, but the way in which it is asked is. For starters, the header question is not detailed enough, as it doesn’t even tell us what language they are compiling until we get to the description. The description itself presents a manner that shows that the user has not done much of their own research into the question, with key words like “I often hear…” and “Sometimes I also hear…”. They also don’t provide enough information on the system and software they’re  using, yet still ask how to enable the warnings without context or images to guide helpful responses. 
The second question from the other user can be classified as a smart question. The question details specifics for the problem they wish to solve, and the description lists out what they’re using, and references the source for their question. The user provides code to allow those wishing to respond to understand where the question arises from. The user also demonstrates their own trials, and even provides an update on top of that. It is also inherently clear that the user is wishing to learn simply to gain that knowledge, and we know this given that the question being asked is them trying to understand a question that had already been asked and answered over a decade ago. One user wishes to simply be told and to know, while the other user wishes to not just know, but to learn and understand.

```cpp
int main() {
    int opt, rno;
    char pname[100]; //char name array
    HotelMgnt hm; //used to call in hm class functions

    do { //do while statement for main menu
        std::cout << "######## Hotel Management #########\n";
        std::cout << "\n1. Manage Rooms";
        std::cout << "\n2. Check-In Room";
        std::cout << "\n3. Available Rooms";
        std::cout << "\n4. Search Customer";
        std::cout << "\n5. Check-Out Room";
        std::cout << "\n6. Guest Summary Report";
        std::cout << "\n7. Exit";
        std::cout << "\n\nEnter Option: ";
        std::cin >> opt;
...}
```

## Proper Perfection

Now for those unfamiliar with the structure of Stack Overflow, there is a rating and score system for questions. Your first thought may be, “Oh, well that means that the question deemed stupid must have a low score”, to which I would present you with the contrary. The example of a smart question I presented had lower ratings and in fact only one response. The stupid question example I discussed had higher ratings and many more responses. So, what does this mean? Does asking a smart question make any difference? Can it hinder the help you receive? Let’s first take a look at the responses for each question to see if we can gain some insight on this.
For the compiler warning question, one response reads, “Not only does handling the warnings make better code, it makes you a better programmer. Warnings will tell you about things that may seem little to you today, but one day that bad habit will come back and bite your head off. Use the correct type, return that value, evaluate that return value. Take time and reflect "Is this really the correct type in this context?" "Do I need to return this?" And the biggie; "Is this code going to be portable for the next 10 years?" Get into the habit of writing warning-free code in the first place”. As you can see, the response does not answer the user’s question. This response reads more like a lecture than a learning opportunity, basically saying do this because it’s good to do. While it’s good advice, it does not help the user with their question and doesn’t even answer it. Therefore, due to the poor quality of the question itself, the user does not receive the insightful help they likely sought out.
For the array speed processing comparison question, here is an excerpt of the only response given to the user: “Several of the answers in the question you link talk about rewriting the code to be branchless and thus avoiding any branch prediction issues. That's what your updated compiler is doing. Specifically, clang++ 10 with -O3 vectorizes the inner loop. See the code on godbolt, lines 36-67 of the assembly. The code is a little bit complicated, but one thing you definitely don't see is any conditional branch on the data[c] >= 128 test. Instead it uses vector compare instructions (pcmpgtd) whose output is a mask with 1s for matching elements and 0s for non-matching. The subsequent pand with this mask replaces the non-matching elements by 0, so that they do not contribute anything when unconditionally added to the sum. The rough C++ equivalent would be: sum += data[c] & -(data[c] >= 128); ...”. The response reflects the specificity provided from the user who posted the question, and clearly explains in detail as to what the user is encountering, the different factors that result in this speed, as well as providing some example code for better understanding. Now, taking all of what has been discussed into account, should we always ask smart questions? Is it ok to ask simple ones?

<img width="250px" 
     class="rounded float-start pe-4" 
     src="../img/questioning/coding1.png" >

## Workplace Wisdom 

From learning about smart questioning, its key components, and detailing these two examples of both a smart and stupid question, I feel that I have learned a lot about when, what, and how to ask questions in a technical manner. While I don’t feel it is always necessary to ask smart questions, especially when it comes to much more simple problems, I do feel that it is a good practice. I myself have been on both sides, with either not getting the help I need due to my lack of providing detail, or not being able to help someone due to this lack of specification and explanation. Moving forward, I feel that I will take a different approach to challenges I face and in asking for help. I want to try to get better at researching the questions I have and relying upon outside assistance if that personal research leads me nowhere. I feel that while we should try to help ourselves, sometimes all we need is another person to help us think about. To summarize this whole long  deep-dive into smart questioning, I present to you the classic saying, “Two heads are better than one”, but maybe add a couple thousand. 
