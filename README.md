# How I Think About Data Work
### Observations on successful (and unsuccessful) data teams after 7 years in the industry

I've spent 7 years doing data work at growth-stage companies: building infrastructure, designing experiments, forecasting revenue, optimizing marketing spend, and creating tools that help teams make better decisions. Along the way, I've learned that data work isn't just a matter of technical skill, but also understanding problems, building relationships, choosing the right tools for the job, and honestly measuring your results.

This piece summarizes how I think about doing data work that creates real value. It's not a prescriptive playbook so much as it is a framework of thinking about how data fits best into an organization that values data-driven decision making.

---

## 1. Problem Selection & Relationship Building

### Deciding Which Problems Are Worth Tackling

Companies, especially small to mid-sized ones, are complex environments that move quickly. You'll never be wanting for all sorts of data requests and data quality tickets, which means you have to be decisive about which tickets and projects you pick up and how you prioritize them.

I triage work by considering three dimensions:

- **Current cost**: What's this problem costing us today? Sometimes it's something obvious, like inventory doesn't know how much stock they have on hand, which means the potential for selling products you don't really have and the practical headaches which ensue. Other times costs are more nuanced or hidden, for example: how do you quantify the potential missed revenue from not having an experimentation framework to an organization that has never run experiments before? I'll also consider opportunity cost: if we work on this problem, what other problems does it prevent or delay us from solving?

- **Future benefit**: If we solve this, what changes? Does it unlock a new capability? Does it improve decision quality? Does it free up capacity for higher-value work?

- **Effort involved**: How hard is this, really? I'm not just talking about technical complexity. Is the data available and clean? Do we have organizational buy-in? Will people actually use this once it's built?

Obviously these three dimensions require making tradeoffs. The most valuable projects are often also the most time consuming. It's important to know which problems your data team defaults to solving so that you can build systems to address the other category. In most organizations I've been a part of larger projects have almost always suffered due to prioritizing ad-hoc requests. One particularly successful system one of my former teams implemented was what we called "20% time," where we took some or most of our Fridays to work on projects we believed were important but hadn't been prioritized. Holding that time with intention required our team to plan ahead to make sure the ad-hoc work was getting done, but also gave them permission to recognize that not every request is a fire drill. Some of that team's most important long-term work came out of that 20% time. Our data infrastructure improved because data enngineers could actually take the time necessary to wrestle with some of the more gangly data pipeline issues we were having, and I was able to build out an entire predictive model and launch it with our marketing team. So, I highly recommend giving your teams permission to prioritize that low-urgency work.

### Building Relationships in Practice

I firmly believe that Data is a service profession first and foremost. You're there to help other teams function better: marketing, product, finance, operations. That means you can't work in a silo. If you're not embedded in what teams are actually doing, you'll build things no one needs or only hear about projects after they're already shipped. And then you'll likely get stuck with the questions about why things didn't go as expected.

Here are some practices I've found valuable for building strong relationships with your SME's:

- **Meet with them regularly.** Not just when they need something from you, but to stay in the loop on what they're working on. Take proactive interest in their work and needs. The most effective data team I've been in has had standing meetings with all business functions; it doesn't have to be weekly, but it has to be consistent.

- **Asking for feedback.** "Do you actually still use that report I built you a month ago?" Sometimes it can be uncomfortable to ask for raw feedback like that. It can be demoralizing to find out that your work isn't being leveraged by the people you did it for. But you were going to find out eventually, so it's better to get it from them so that you can actually talk through what isn't working for them. On top of that, it's really useful to get close knowledge of your partner-team's consistent pain points. Ask them what they're struggling with this week and see if they're still having issues a week or a month from now. Sometimes that's the best indicator that it's worth making a ticket.

- **Probing for gaps.** Where is trust lacking in the data? Where is information lacking? Where are decisions being made on gut feel because the numbers aren't there or aren't trusted? 

### Questions I Ask When Engaging With a New Team

These are some questions I've learned to ask to operational teams I'm partnering with, either as I'm onboarding with them or as occasional touch-bases to see if things have changed:

1. **"What do you spend a lot of time on, when it comes to reporting or decision-making?"** I'm probing for repetitive work that could be automated. If someone is manually pulling the same numbers every week, that might be something I can spend a day on to give them a day of their time back every week.

2. **"How do you feel about the data you have right now?"** This tells me about trust. If they say "I never know if the numbers are right," I've got a data quality problem I can take back to Data Engineering or resolve in the metrics layer. If they say "I have data but I don't know what it means," then I can either work on how it's presented or it might be an opportunity to train them on a hard-to-grasp tool or concept.

3. **"Are there any decisions you have to make regularly that feel like you have to rely too much on your gut?"** This helps me understand where I can make future-facing impact. Sure sometimes these are still descriptive problems, but often the answers to this question lead to prescriptive or predictive projects, which is likely why your company has a data team in the first place.

4. **"If you had a data genie that could answer any question with 100% certainty, what would you ask it first and why?"** I like probing with an open-ended question every once in a while and especially when I'm just starting out with a team (Marketing people will love this question, but you might get an eye roll from Operations or Finance, but who cares). Sometimes it reveals high-effort, high-impact projects worth considering. Other times it reveals a key flaw in data trust that will enable you to build a stronger relationship with that function. Either way it helps me understand what's really important to that particular team, which will help me with all the rest.

---

## 2. Execution & Project Types

### Choosing the Right Tool for the Problem

Once you've identified a problem worth solving, the next question is: **What kind of project is this?**

There are some analysts out there who are just dying to find a way to use a neural-net to answer every question, just like there are some who wish they could always just build a dashboard and call it a day. But we all know there's not a one-size-fits all answer. What it took me some time to realize though is that the textbook 'best' solution for a problem might not always be the tool you actually __should__ use in your situation.

Here's how I break it down:

- **Deep understanding of the problem.** What are we actually trying to solve? What does success look like? What happens if we don't solve it? This is what a lot of the above sections are about. Problem-framing helps me set up upper and lower limits for the work: what's 'good enough' look like and how far do we need to go to hit the highest expectation? (e.g. maybe someone will use your predictive model if it's at least 85% accurate, but they'll shout for joy if you get over 95% accuracy, while hitting 99.9999% won't do anything for them because it's overkill)

- **Available data.** What do we actually have? Is it clean? Is there enough of it? Is it the right data? Sometimes I've started building out a project timeline only to discover a week in that the data isn't reliable or doesn't exist. Now I validate data quality and coverage upfront. This also dictates the sort of solutions you can choose from.

- **Cost-benefit.** What's the potential business impact, realistically? Does it justify a complex solution, or is a simpler approach good enough? "Good enough" is underrated by greener data workers IMHO, so interns, listen up.

I find having these three bases covered lets me evaluated solutions that I know will be promising upfront without wasting effort. Who knows, sometimes the heuristic model will beat out your fancy neural-net, and that's fine, because at the end of the day it's about how well we solve the problem, not the tool we use, that counts.

### My Decision Framework (Such As It Is)

I don't have a rigid decision framework, but here's how I generally approach making decisions for data projects:

- **Identify short and long-term goals.** I refuse to make short-term gains at substantial long-term expense. That means I'm not afraid advocate for a quick-and-dirty approach if speed matters more than elegance, but I will make sure it's not at the expense of future data quality, tech-debt, or scalability concerns.

- **Understand your environment.** What's the company's maturity? What's the team's capability? What's realistic given the constraints? What will knock the socks off of leaders at a Series A might seem like a waste of time at a scale-up, not to mention that they have different budgets, priorities, and constraints.

- **Do the best with what you have.** Optimize for impact given the constraints: I've worked at companies with messy data and limited resources. You can still create value; you just have to be smart about where you focus.

- **Experiment early.** Testing assumptions early aligns decisions to desired outcomes and reduces risk. Green analysts jump into the deep end head first. I know because I've done it. But now I've learned that it's almost always more effective to approach projects iteratively, especially when you're doing model development.

### The Types of Data Work I Do

To shift the focus back onto my work and how it fits into this framework, I've done a variety of data work over the years across the whole stack:

- **Infrastructure & data/analytics engineering**: dbt pipelines, semantic layers, self-service BI platforms. This is the __sine qua non__ of our profession; if you have bad or inaccessible data, nothing matters until you fix that problem.

- **Predictive modeling**: Revenue forecasting (LSTM), customer segmentation (clustering), churn prediction. These are the "classic" ML projects, but they're only valuable if they actually inform decisions.

- **Marketing analytics**: Media mix modeling, multi-touch attribution, incrementality testing. This is where I've spent a lot of time. Marketing measurement is hard because causality is messy, but getting it right (or more accurately, getting it 'least wrong') has huge ROI.

- **Experimentation**: A/B test design, multi-armed bandits, bespoke experimental design. I'm a stickler for experimental rigor because it's one of the easiest data processes to be sophomoric about. Everyone thinks experimentation is simple, until you try to tell them why their sample size of fifty doesn't have the power to detect the effect size they're looking for.

- **Custom data products**: Streamlit apps, automated reporting, web scraping frameworks, API integrations. Sometimes the best solution isn't an analysis; it's a tool that enables someone else to do their job better. In other words, sometimes data professionals get to dress up as entry-level software engineers for a week, and honestly it's pretty fun.

---

## 3. Communication & Adoption

### How to Get People to Actually Use What You Build

You can build the most technically elegant solution in the world, but if no one uses it, it's worthless. I've learned this the hard way. Here's what I've learned about adoption:

- **Build strong relationships with the people on the front lines of the business.** If they trust you, your work can transform the business. If they don't, it won't. Trust comes from delivering on commitments, being honest about limitations, and showing up with consistency and expertise. It's okay to lean heavily on saying, "let me get back to you on that" in your first six months on the job, but once you're ingrained in the system, be the person those SME's can rely on to predict roadblocks before they happen and offer solutions proactively. I'm not saying you can't ever take time to build a robust answer, but if you don't have your house in order, it will be hard for other teams to trust you.

- **Build things that actually solve real problems.** Most of the time if you build something people don't use, you've failed to address a real pain point. This is hard because sometimes people think they're asking you for a solution to a real pain point when it really doesn't matter that much. Maybe it's a curiosity, not a need. Maybe they think they need a dashboard when what they really need is a one-time analysis. That's where the upfront discovery questions help a lot.

- **Develop an appropriate adoption and onboarding plan.** Sometimes tools aren't adopted because people are so ingrained in their old way of doing things that switching feels like more effort than it's worth. That's where having an onboarding plan and providing continuous accountability and support helps.

  Meeting regularly with a team and asking them if they're using the new dashboard you built is helpful, but only if they can also lean on you to help them when the friction mounts. If you build something, hand it off, and disappear, don't be surprised when usage drops to zero three weeks later. I've found a lot of success in offering "data office hours" so that people can always have a structured place to go with questions and issues. Will it increase your ad-hoc requests? Yes. But it will also profoundly increase organizational trust in the data team.

- **Design for your audience and purpose.** A dashboard for an executive needs to be different from a dashboard for an analyst. Executives want high-level trends and simple narratives. Analysts want to drill down, explore, and validate assumptions. If you don't understand who you're building for, you'll build the wrong thing.

  But sometimes your audience expects a one-dashboard-fits-all solution. I've learned to identify the line when scope-creep is close to killing a perfectly acceptable data product. When I'm nearing that point I try to be ready to go with proactive suggestions. For example: "This dashboard is really designed to offer tactical weekly insights that impact day-to-day operations. I'm happy to build out something that will give you high-level quarterly numbers, but if we add it here, I think it will make both of those tasks more difficult. What do you think?"

### What Makes a Project Get Adopted vs. Ignored

When I do post-mortems on projects that didn't get adopted, it usually boils down to one of three things:

1. **Misunderstanding of the problem.** You solved the wrong thing. Maybe you built a forecasting model when what they really needed was better visibility into current performance. Maybe you built a complex segmentation when simple cohort analysis would have sufficed.

2. **Choosing a problem without real impact.** The pain point wasn't actually painful enough. It seemed important in theory, but in practice, people were fine living with the status quo. This is why I probe so hard on "what decisions would change if you had this data?"

3. **Poor onboarding or support.** You built it and disappeared, expecting them to figure it out. Or you built something that requires too much manual work to maintain. Or you didn't train people on how to actually use it. All of these are fixable with better planning upfront.

---

## 4. Measurement & Learning

### Measuring Success Across Different Project Types

You have to have a holistic view of what success looks like and how you might measure it. Not everyone is a digital marketer drowning in quantitative data. Here are some different ways to define and measure success that I've found productive:

- **Efficiency gains**: Did this save time? Reduce manual work? Free up capacity for higher-value tasks? _Example: automating a weekly report that took 8 hours to produce now takes 1 hour. That's 7 hours/week of analyst capacity freed up, which is real value._

- **Cost reduction**: Time costs, monetary costs, opportunity costs. _Example: optimizing cloud infrastructure queries to reduce BigQuery costs by 25%. Or preventing a bad promotional decision that would have cost $20K in wasted margin._

- **Value to the bottom line**: Direct or indirect revenue impact. This is the hardest to measure cleanly, since everyone will want to claim credit. But sometimes you can find a clean signal, and even if you can't, sometimes business logic will tell you that an outcome is valuable even if you can't perfectly quantify it. _Example: a forecasting model that improves cash flow management, or an attribution model that reallocates marketing spend to higher-ROI channels._

- **Time to value**: How quickly did this start mattering? Sometimes a quick-and-dirty solution that delivers value in two weeks is better than a perfect solution that takes three months.

- **Capability creation**: Did this enable work that wasn't possible before? Sometimes you're building infrastructure that doesn't have immediate ROI but creates the foundation for future work. _Example: building a dbt pipeline and semantic layer that lets analysts work faster with cleaner data._

But here's the thing: sometimes you build something that just reduces friction. A framework to enable teams to experiment on their own, for example. That will have measurable success factors in the long run (faster iteration, better decisions), but there's also the qualitative success metric of empowering teams to be more self-sufficient, which is a good in itself.

### Learning From Projects That Didn't Land

Nobody does post-mortems enough, at least in my experience (FAANG friends, tell me it's better up there, please). If you don't actually sit with what went wrong, your failure will only ever be that: a failure. You have to actually get feedback, look at what happened, work through key inflection points (whether in decision-making or execution), and develop systems (where appropriate) to mitigate them, without being overly bureaucratic or creating processes that slow everyone down.

I've had projects that didn't land. Media mix models that never got deployed because leadership changed mid-project. Segmentation work that sat unused because the organization wasn't ready to act on it. Forecasting that was accurate but didn't lead to proactive decisions because the stakeholder was risk-averse.

Each taught me something:

- **Sometimes the problem is technical.** Wrong model for the data. Bad assumptions. Overfitting. These are fixable with better methodology.

- **Sometimes the problem is organizational.** No buy-in from leadership. No one with authority to act on the insight. Competing priorities. These are harder to fix and often require better stakeholder management upfront, and can sometimes still be out of your control.

- **Sometimes the problem is timing.** Great work, wrong moment. The organization wasn't ready. Budget got cut. Leadership changed. These are often outside your control, but recognizing them helps hone your instincts for when teams are ready and able to act and when they aren't.

The key is being honest about which one it is, learning from it, and not making the same mistake twice.

---

## 5. Organizational Considerations

### Red Flags and Green Flags

Not all companies are ready for data work. And not all companies that say they're data-driven actually are. I've learned to pay attention to signals that tell me whether an organization will actually use what I build.

**Green flags I look for:**

- **How they handle data-driven insights that counter their intuitions.** For better or worse our brains are wired with myriad pattern-recognition systems which aided us in survival in times past. The unfortunate truth when it comes to data work is that most of these pattern-recognition systems are maladapted for analyzing data; it's why we call them biases. Whether survivorship bias, selection bias, confirmation bias, even Simpson's Paradox (which isn't a bias, but which can still trip up our intuitions), all of these come from bindspots in our default behaviors or beliefs.

  If you showed a leadership team the results of an experiment which contradicts their bias, would they accept that the numbers should override common intuition? It's fine to revisit the data process in the face of unintuitive results. That's a healthy response. But if you have confidence in your data team and your process, and the numbers do check out under further scrutiny, a data-driven team lets the numbers lead the decision-making. Not gut feel.

- **How data is treated organizationally.** It's really easy to have a lot of numbers in front of you but not actually use them in your decision-making process. I look for signals like: Does the data team report to senior leadership instead of being buried under IT or engineering? Do executives actually reference data in strategic discussions? Are data requests coming in proactively ("We're planning X, what does the data suggest?") rather than reactively ("We did X. Tell us how the data say we did.")?

- **Where teams ask data questions in their process.** If you only ever use your data team for retrospective work, you fundamentally don't understand how data should integrate into an organization. The best data teams are involved early: in product roadmap discussions, in marketing planning, in operational strategy. The earlier data is included, the more influence it has.

**Red flags:**

- Leadership says "we're data-driven" but the data team isn't consulted on major decisions.
- Data requests are always urgent and reactive, never strategic.
- No one can articulate which metrics drive results, or believes any metric is a good metric.
- Analysts are penalized for delivering results someone doesn't want to hear.
- The data infrastructure is neglected (dirty data, broken pipelines, no single source of truth, analysts spending 80% of their time validating numbers instead of analyzing them).

These aren't always dealbreakers. Sometimes you can fix them if you have executive support. But you need to go in with eyes open about what you're walking into.

### What Makes a Company Ready for Data-Driven Work

Three things need to be true:

1. **Quantity of data.** Without this, your analysts can't do anything. You need sufficient volume and history to do meaningful analysis. If you're a three-month-old startup with 100 customers, you're not ready for sophisticated modeling. You need time to accumulate signal.

2. **Systems to support a data function.** Without this, no one will give data the room to operate. That means budget, headcount, and organizational respect for the function. It means data has a seat at the table, not just a support role. It means leadership is willing to invest in tooling, infrastructure, and people.

3. **Dependable data pipeline.** Without this, your analysts will spend all their time validating numbers instead of actually analyzing them. If every analysis starts with "first I have to clean the data and reconcile three different sources," you're not set up for success. Clean, reliable, well-documented data is foundational.

If a company doesn't have these three things, you can hire the best data person in the world and they'll either burn out or accomplish nothing. I've seen it happen. It's not their fault. The organization just isn't ready.

---

## Final Thoughts

Data work isn't only technical. It's a service-function that understands problems deeply, builds relationships with the people it's serving, chooses the right tools for the job, communicates clearly, and honestly measures its outcomes, good or bad.

I've learned the hard way that even the best analysis, the most rigorous model, or the most elegant infrastructure is worthless if it doesn't get used. And whether it gets used depends as much on organizational culture as it does on technical execution.

That's why I'm selective about where I work. I want to be somewhere that:

- Actually listens to data
- Empowers data teams to influence decisions
- Measures success on impact, not activity
- Has the infrastructure and organizational readiness to support data-driven work

**If that sounds like your organization, let's talk.**

[LinkedIn](https://www.linkedin.com/in/ben-wachtel/)
[Portfolio](https://www.datascienceportfol.io/bwachtel)
[Website](https://www.bwachtel.com/)
