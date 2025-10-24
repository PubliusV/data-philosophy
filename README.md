# How I Think About Data Work
### Observations on successful (and unsuccessful) data teams after 7 years in the industry

I've spent 7 years doing data work at growth-stage companies: building infrastructure, designing experiments, forecasting revenue, optimizing marketing spend, and creating tools that help teams make better decisions. Along the way, I've learned that data work isn't just a matter of technical skill, but also understanding problems, building relationships, choosing the right tools for the job, and honestly measuring your results.

This guide summarizes how I think about doing data work that creates real value. It's not a playbook (every company is different), but it's a framework I return to when deciding what to work on and how to approach it.

---

## 1. Problem Selection & Relationship Building

### Deciding Which Problems Are Worth Tackling

Not all problems are created equal. You could spend months building the perfect model for a problem that doesn't actually move the needle. Or you could get swamped addressing a hundred small, easy problems that feel productive but don't add up to much.

I triage work by considering three dimensions:

- **Current cost**: What's this problem costing us today? Sometimes it's obvious (manual reporting consuming days/week of analyst time). Other times it's hidden (decision-makers flying blind because they don't have the right data, leading to suboptimal choices that compound over time). I'll also consider opportunity cost: if we work on this problem, what other problems does it prevent or delay us from solving?

- **Future benefit**: If we solve this, what changes? Does it unlock a new capability? Does it improve decision quality? Does it free up capacity for higher-value work? The key is being honest about whether the benefit is real or aspirational.

- **Effort involved**: How hard is this, really? I'm not just talking about technical complexity. Is the data available and clean? Do we have organizational buy-in? Will people actually use this once it's built?

Some problems are really promising but really big. Others are easy wins, but there are so many of them it's easy to suddenly get swamped doing busywork. The key questions I return to: **What must get done, even if it doesn't feel urgent?** These projects require advocacy and endurance – you have to fight to keep them moving, and that requires being able to articulate their value. **For what feels urgent, will it really make a difference?** Managing these projects requires the ability to say "no." It's the only way you make room for the low-urgency, high-importance tasks.

This is where experience matters. Early in my career, I'd chase shiny problems or drown myself in ad-hoc requests because I felt too junior to say "no" (managers, pay attention, sometimes you're the one who has to say it instead of your direct report). Now I'm more disciplined about understanding whether solving a problem will actually change behavior and have some experience behind me to advocate for a priority list I feel good about.

### Building Relationships in Practice

Data is a service profession first and foremost. You're there to help other teams function better: marketing, product, finance, operations. That means you can't work in a silo. If you're not embedded in what teams are actually doing, you'll build things no one needs or only hear about projects after they're already in post-mortem.

Here's what building relationships actually looks like in practice:

- **Meeting with teams regularly.** Not just when they need something from you, but to stay in the loop on what they're working on. The most effective data team I've been in has had standing meetings with all business functions; it doesn't have to be weekly, but it has to happen regularly. It's hard to offer data help for a project you never hear about.

- **Asking tough questions.** "Do you actually still use that report I built you a month ago?" It's uncomfortable, but necessary. If they're not using it, we should either fix it or kill it. Maintaining unused infrastructure is a waste. Plus, once you get over that pain of that shiny new report you spent weeks on getting abandoned, you can add it as another data point in your dataset of effective vs. ineffective data products. If you never asked, you'd never know.

- **Probing for gaps.** Where is trust lacking in the data? Where is information lacking? Where are decisions being made on gut feel because the numbers aren't there or aren't trusted? These gaps are where data work can create real value, but you only find them by asking.

- **Staying operational.** The best data insights come from understanding the day-to-day reality of how teams work. If you only parachute in for "strategic projects," you'll miss the small opportunities that compound into big wins.

### Questions I Ask When Engaging With a New Team

When I start working with a new team, I ask questions designed to uncover both quick wins and strategic opportunities:

1. **"What do you spend a lot of time on, when it comes to reporting or decision-making?"** I'm probing for repetitive work that could be automated. If someone is manually pulling the same numbers every week, that's low-hanging fruit.

2. **"How do you feel about the data you have right now?"** This tells me about trust. If they say "I never know if the numbers are right," that's a data quality problem. If they say "I have data but I don't know what it means," that's a communication problem.

3. **"Are there any decisions you have to make regularly that feel like you have to rely too much on your gut?"** This surfaces places where better data or better reporting would actually change behavior. These are high-value opportunities.

4. **"If you had a data genie that could answer any question with 100% certainty, what would you ask it first and why?"** This is the "blue sky" question. Sometimes it reveals high-effort, high-impact projects worth considering. Other times it reveals a key flaw in data trust that will enable you to build a stronger relationship with that function.

---

## 2. Execution & Project Types

### Choosing the Right Tool for the Problem

Once you've identified a problem worth solving, the next question is: **What kind of project is this?**

I've learned that there's no such thing as a universally optimal solution. It's all well and good to know how to build an ARIMA or LSTM forecasting model, but if you only have six months of noisy data, its utility is going to be minimal at best. Sometimes a simple heuristic model is a better fit. I've learned over the years to refuse to let shiny models distract me from what tool might be the best fit for the task at hand.

There's also the cost-benefit analysis. An advanced or time-consuming solution might be the technically "optimal" solution, but if you consider the potential business impact, sometimes the upside is too small to support the work required for it.

I find the decision comes down to:

- **Deep understanding of the problem.** What are we actually trying to solve? What does success look like? What happens if we don't solve it? I spend a lot of time in this phase because getting it wrong here cascades into waste later.

- **Available data.** What do we actually have? Is it clean? Is there enough of it? Is it the right data? I've been burned by starting ambitious projects only to discover the data isn't reliable or doesn't exist. Now I validate data quality and coverage upfront. This also dictates the sort of solutions you can choose from; hence the forecasting discussion above.

- **Cost-benefit.** What's the potential business impact, realistically? Does it justify a complex solution, or is a simpler approach good enough? "Good enough" is underrated by greener data workers IMHO, so interns, listen up.

### My Decision Framework (Such As It Is)

I don't have a rigid decision framework, but here's how I generally approach making decisions for data projects:

- **Identify short and long-term goals.** I refuse to make short-term gains at substantial long-term expense. That means I'm not afraid advocate for a quick-and-dirty approach if speed matters more than elegance, but I will make sure it's not at the expense of future data quality, tech-debt, or scalability concerns.

- **Understand the place you're in.** What's the company's maturity? What's the team's capability? What's realistic given the constraints? A Series A startup with two engineers has different needs than a Series C company with a 50-person tech team.

- **Do the best with what you have.** Optimize for impact given the constraints: I've worked at companies with messy data and limited resources. You can still create value; you just have to be smart about where you focus.

- **Experiment early.** Testing assumptions early aligns decisions to desired outcomes and reduces risk. If I'm not sure whether a complex model is worth building, I'll prototype a simpler version first to validate that the approach makes sense (and that the problem is important enough to warrant the effort) before investing in production-grade work.

### The Types of Data Work I Do

Over the years, I've done a range of data work:

- **Infrastructure & analytics engineering**: dbt pipelines, semantic layers, self-service BI platforms. This is foundational work. If your infrastructure is broken, nothing else matters.

- **Predictive modeling**: Revenue forecasting (LSTM), customer segmentation (clustering), churn prediction. These are the "classic" ML projects, but they're only valuable if they actually inform decisions.

- **Marketing analytics**: Media mix modeling, multi-touch attribution, incrementality testing. This is where I've spent a lot of time. Marketing measurement is hard because causality is messy, but getting it right has huge ROI.

- **Experimentation**: A/B test design, power analysis, statistical rigor frameworks. I'm a stickler for experimental rigor because I've seen too many bad decisions made from poorly designed tests.

- **Custom data products**: Streamlit apps, automated reporting, web scraping frameworks, API integrations. Sometimes the best solution isn't an analysis; it's a tool that enables someone else to do their job better.

Each has its place. The key is choosing the right ones for the place your organization is in. Don't expect your first data hire to be building experimentation frameworks or automated RAG systems in their first year. Get the foundation built first, so that your big projects have the impact you need and expect.

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

**Post-mortem, post-mortem, post-mortem.**

If you don't actually sit with what went wrong, your failure will only ever be that: a failure. You have to actually get feedback, look at what happened, work through key inflection points (whether in decision-making or execution), and develop systems (where appropriate) to mitigate them, without being overly bureaucratic or creating processes that slow everyone down.

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
