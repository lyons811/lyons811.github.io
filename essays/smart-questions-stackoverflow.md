---
layout: essay
type: essay
title: Smart Questions, Smart Engineers
# All dates must be YYYY-MM-DD format!
date: 2024-09-11
published: true
labels:
  - StackOverflow
  - Questions & Answers
---

<img width="300px" class="rounded float-start pe-4" src="https://t3.ftcdn.net/jpg/00/54/65/16/360_F_54651607_OJOGbrFBB3mDTpZDKmdjjR94lsbZMTVa.jpg">

## What are smart questions?

Smart questions are exactly what they sound like. They're asked in a way where someone who knows the answer will be able to immediately answer them without having to ask for additional information. Smart questions save time for everyone involved, and knowing how to ask one is a skill that may not be immediately apparent to some. From my experiences, most of the classes I've taken have never really gone into detail about what makes a good question; they just state that there are no such things as "dumb questions". I agree with that statement, but I believe there are also such things as "incomplete questions". These are questions where only basic, limited information is given, with the expectation that it's enough for an answer. For some fields, such questions might suffice. But in the realm of software engineering, such questions almost always require additional information from the questioner to produce an answer that satisfies the inquiry.

## The importance of smart questions in software engineering

In the field of software engineering, the ability to ask smart questions is crucial. It not only demonstrates a developer's problem-solving skills but also shows respect for the time and expertise of those they're seeking help from. Eric Raymond's essay "How to Ask Questions the Smart Way" provides valuable guidelines for effective interaction within the open-source community, and these principles apply equally well to platforms like StackOverflow.

## A tale of two questions: Smart vs. Not-so-smart

To illustrate the impact of asking questions the smart way, let's examine two real-world examples from StackOverflow.

### The not-so-smart question

[Unfortunately MyApp has stopped. How can I solve this?](https://stackoverflow.com/questions/23353173/unfortunately-myapp-has-stopped-how-can-i-solve-this/23353174#23353174)

This question demonstrates several pitfalls of asking questions the "not smart" way:

1. Vague title: The title doesn't provide any specific information about the problem.
2. Lack of context: The asker doesn't mention what kind of application they're developing, what platform they're using, or what they've tried so far.
3. No error messages or logs: There's no information about any specific error messages or stack traces that could help diagnose the issue.
4. No code provided: Without seeing any code, it's impossible for others to identify the source of the problem.

The question in its entirety reads:

"I am developing an application, and everytime I run it, I get the message:
Unfortunately, MyApp has stopped.
What can I do to solve this?"

This question violates several of Raymond's principles for asking smart questions. It shows a lack of effort in diagnosing the problem, provides insufficient information, and doesn't demonstrate any attempt to solve the issue independently before seeking help.

### The smart question

[ArrayIndexOutOfBoundsException with custom Android Adapter for multiple views in ListView](https://stackoverflow.com/questions/2596547/arrayindexoutofboundsexception-with-custom-android-adapter-for-multiple-views-in)

In contrast, this question exemplifies many aspects of asking questions the smart way:

1. Specific and descriptive title: The title clearly states the exact error and the context in which it occurs.
2. Detailed problem description: The asker provides context about what they're trying to achieve and the specific error they're encountering.
3. Code included: The relevant code is shared, making it easier for others to understand and diagnose the issue.
4. Error message provided: The exact error message and stack trace are included, giving crucial information for troubleshooting.
5. Platform and version information: The asker mentions they're targeting Android 1.6, which helps contextualize the problem.

The question begins with a clear explanation of the goal:

"I am attempting to create a custom Adapter for my ListView since each item in the list can have a different view (a link, toggle, or radio group), but when I try to run the Activity that uses the ListView I receive an error and the app stops."


It then provides the relevant code:

```kotlin
public class MenuListAdapter extends BaseAdapter {
 private static final String LOG_KEY = MenuListAdapter.class.getSimpleName();

 protected List<MenuItem> list;
 protected Context ctx;
 protected LayoutInflater inflater;

 public MenuListAdapter(Context context, List<MenuItem> objects) {
  this.list = objects;
  this.ctx = context;
  this.inflater = (LayoutInflater)this.ctx.getSystemService(Context.LAYOUT_INFLATER_SERVICE);
 }

 @Override
 public View getView(int position, View convertView, ViewGroup parent) {
  Log.i(LOG_KEY, "Position: " + position + "; convertView = " + convertView + "; parent=" + parent);
  MenuItem item = list.get(position);
  Log.i(LOG_KEY, "Item=" + item );

        if (convertView == null)  {
            convertView = this.inflater.inflate(item.getLayout(), null);
        }

        return convertView;
 }

 // ... (other overridden methods)
}
```
The asker also includes the exact error message:
```kotlin
java.lang.ArrayIndexOutOfBoundsException
  at android.widget.AbsListView$RecycleBin.addScrapView(AbsListView.java:3523)
  at android.widget.ListView.measureHeightOfChildren(ListView.java:1158)
  at android.widget.ListView.onMeasure(ListView.java:1060)
  at android.view.View.measure(View.java:7703)
```
This level of detail and preparation demonstrates respect for the community's time and increases the likelihood of receiving helpful, targeted responses.

## The impact of question quality on responses

The quality of the questions directly influences the quality and efficiency of the responses received. In the case of the "not-so-smart" question, the responses are generally vague and cannot provide specific solutions due to the lack of information. Many answers request more details or suggest generic troubleshooting steps.
On the other hand, the "smart" question received detailed, specific responses addressing the exact issue. The accepted answer not only solved the problem but also explained the underlying cause, providing valuable learning for the asker and future readers.
