# Building AI/ML Products for Data Scientists
The last decade has been phenomenal in the growth of Data Science as a discipline. Enormous strides have been made in almost all phases of data science, resulting in some of the biggest innovations in recent times.
As the exploration phase matures, there is increasing focus on moving these data science findings into products and solutions usable in the market. These solutions and products need to be reliable, resilient, scalable, and most important of all, able to stand the test of time.
Software development practices have been around for more than 40 years now, and software delivery models have gone through multiple phases and have stabilized enough that more and more of our day-to-day activities are software driven.
As AI/ML teams move from a prototyping/pilot phase to a product development phase, here are a few pointers, customized to a data science project, for building reliable AI/ML-based products.
## Understand the difference between a prototype and a software product
More often than not, many data science projects today start and end as a pilot or prototype, never being deployed to a larger audience. With a pilot/prototype, the output is needed in a really short time, and the goal is getting things to work rather than maintainability or reliability.
On the other hand, when you build an AI/ML product consumed by millions of users, the model or the software you build around it will be used by customers for at least 3–4 years. The goal here is not just to get the functionality in place, but to ensure that it's reliable, scalable, and maintainable.
A minor additional loop in your inference code might not be a big issue while building a prototype for quick use, but it could spiral into a serious memory issue when scaled up and used over a longer time.
Understanding the difference between the two is fundamental to building a resilient AI/ML solution.
## Any module you write should be self-testable
Just like any module in a software engineering life cycle, any component built in an ML lifecycle must be self-testable and confident of its own correctness, without depending on the consumers of the module. For example, code that replaces missing data with the mean of a column should be testable independent of the nature of the data or the model selected.
## Integrate and deploy as soon and as often as possible
More often than not, data science development is still a fractured process where the model comes out first after multiple iterations, and the MLOps part comes later as an afterthought.
It is always better to test the end-to-end pipeline, even with a baseline model, then continue to iterate and improve the model. This lets you fail fast and fail often.
## Always maintain a single source of truth (SST) for everything
A commonly overlooked activity in any data science development project is maintaining a single source of truth (SST). This applies to every component of the development process.
Have a single set of code, versioned and developed from a GitHub repository the entire team runs against, rather than separate copies on each developer's machine.
Have a single point from which the dataset is versioned, controlled, and downloaded for development by the entire team.
This solves a host of integration issues down the line.
## Code defensively (whatever can go wrong will go wrong)
Model development and feature engineering often assume the data will be in a specific format, and data cleaning is built on that assumption. But more often than not, the data won't be exactly what you expect. A single piece of bad data can throw your pipeline off. It's essential to anticipate this and code defensively.
## Do code reviews
Machine learning pipelines have a greater chance of failure due to cascading data processing issues that affect model performance.
Catching simple logical mistakes in code can meaningfully improve model performance.
Regular code reviews keep this in check.
## "Fix and prevent" bugs
Every time you find a bug — in the model code, the data processing code, or the inference code — don't just fix it. Add logging and other safeguards so similar bugs don't recur in that area.
## Never hardcode
It's convenient to hardcode API keys and data access keys in a notebook during exploration, but it's a dangerous practice — once that code moves to production, a single piece of unencrypted, sensitive information can jeopardize the entire application.
## Keep code future-friendly
Even when writing code in a notebook or a Python script, keep it future-friendly. As new libraries and techniques emerge, code changes rapidly, so it's important to capture your design considerations and original intent — either through clear comments or unit tests.
## Document all decisions and make them available to the whole team
Data science teams tend to be more siloed than traditional development teams, so any decision you make — say, choosing a specific hyperparameter for a specific reason, or dropping a feature — should be made known to the entire team.
Modern collaboration tools like MS Teams and Slack make this easier, and are preferable to traditional Word-based documentation since they're searchable and easier to reference.
## Use the right tool for the right purpose
People are creatures of habit and default to the tools they're comfortable with for everything. In an age of fast-changing SaaS tools, using the same tool for every purpose and forcing it to do things it wasn't built for is self-defeating and time-consuming. For example, AWS SageMaker is a great tool for developing and deploying models, but if you're focused on big data processing, SageMaker isn't the best fit — AWS Glue or Spark might suit you better.
## Don't repeat yourself (DRY)
A lot of data scientists end up doing the same work over and over. Activities like stop-word removal, lemmatizing, or writing PyTorch boilerplate training code are repetitive and unproductive, and should be avoided. Feature stores and tools like PyTorch Lightning are good steps toward DRY in a data science project.
## Maintain the sanctity of production
Modifying a live production system directly — adding a feature or tweaking a hyperparameter — might be convenient, but it's always a bad idea. Always respect the sanctity of production, and make changes only after thorough testing in other environments.
## Make it work, then make it great
Data science projects are a never-ending, iterative process. While it's a noble goal to aim for close to human-level accuracy on a model, it's important not to go overboard, or the project will remain stuck in development and the model will never ship.
