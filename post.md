## The early days

When you're launching the initial, MVP version of your product, user analytics is pretty simple. Usually you'll setup [Google Analytics](http://www.google.com/analytics/), and add a well-known, all-in-one user analytics tool like [Mixpanel](https://mixpanel.com/), [KISSmetrics](https://www.kissmetrics.com/), [Popcorn Metrics](http://www.popcornmetrics.com/), [Flurry](http://www.flurry.com/), [Heap](https://heapanalytics.com/), or [Churnbee](https://churnbee.com). All good tools for what they provide.

You won't have a good plan for what you want to measure, so you just make sure that signups are making it into the system, and maybe a few other events, for good measure.

And since you don't really have much to look at yet, or any historical context to compare your numbers with, you just forget about metrics for a while. You're on the free tier — so no worries — back to building product.

At some point, though, you'll get an uneasy feeling that you're not really using the full power of the tool, especially once you outgrow the free tier, and start spending real money. Around the same time, you'll also begin to have questions that aren't answerable by these all-in-one tools.

## The crisis

Eventually you get a question like this:

> "How's your weekly active user retention look?" - a sophisticated investor 

Shit just got real. Time to get on your A game.

You then start trying to learn about the crazy world of modern analytics, and discover that tools come in all shapes, sizes, and costs; the options are daunting. 

---

## Option 1: Move to an upstream all-in-one tool

I hear good things about [RJMetrics](https://rjmetrics.com/), though I don't have any direct experience. It might be a good option for you, if you want to minimize complexity. There are probably other options. I'm personally not a big fan of this option, so onto the next one...

---

## Option 2: Add-ons

These tools provide a nice layer of information with minimal effort, and without having to ship your data off to them.

Engagement/Churn Prediction — [Preact](http://www.preact.com/), [Framed Data](https://www.framed.io/) — sits on top of [Salesforce](http://www.salesforce.com/), [Desk.com](http://www.desk.com/), [Mixpanel](https://mixpanel.com/), etc.

SaaS metrics — [ChartMogul](https://chartmogul.com/), [BareMetrics](https://baremetrics.com/) — sits on top of [Stripe](https://stripe.com/), etc.

Some of these options can be pricey.

---

## Option 3: Establishing your own events datawarehouse

You will eventually need to take control of your own data, and it usually starts with bad news.

You probably haven't been recorded everything you should have been, or you have been pushing data to a tool that you can't easily get your data back out of.

We find quite often, however, that your historical data is incompatible with the schema that you want to use going forward. It's best to discover this as early as possible.

### Data Collection

Many startups are light on internal data science capability. If your event volumes are low, [Keen IO](https://keen.io/) is great as your first user events datawarehouse. It has very usable tools to get data in and out, and the pricing is reasonable (with a free bottom tier).

If you're already at high event volumes, and have people with good SQL-fu on your team, [Snowplow Analytics](http://snowplowanalytics.com/) is a powerful option that results in a clean, tidy datawarehouse in [Amazon Redshift](http://aws.amazon.com/redshift/), which is accessed via a subset of PostgresSQL commands, and unlocks a world of high-end data processing and analysis (both in features and cost).

[Astronomer](http://astronomer.io) and [Segment](https://segment.com/) help you get your events into Amazon Redshift. These tools also push your data to other tools, so we find it extremely useful to add a layer of flexibility to reduce vendor lock-in, and to save programmer time.

### Analysis and visualization

If you have a data scientist (or someone who can play one on TV) and your own datawarehouse, you can leverage an impressive collection of cloud-based analysis tools, including [Mode](https://modeanalytics.com/), [Looker](http://www.looker.com/), [Chartio](https://chartio.com/), and [Datahero](https://datahero.com/) (in addition to traditional tools like [R](http://www.r-project.org/) and [Tableau](http://www.tableau.com/)).

If you're light in the data science department, and using Keen IO, you take advantage of some [Phil Libin style cohort visualizations ](https://www.airpair.com/keen-io/posts/making-phil-libin-style-cohort-visualizations-available-to-everyone) which connect directly to your datawarehouse, and provide end-to-end analysis and visualization, inspired by the best practices of world-class product owners. [Learn more about that solution](https://cohorts.astronomer.io).

Also, Keen IO provides an [open source dashboard](https://github.com/keen/dashboards) that you can use as a basis for rolling your own custom analytics, in a more efficicient way.

---

## Option 4: Logfile analysis 

A [tweet by Kerry Rodden](https://twitter.com/kerryrodden/status/579397570100785152) was the inspiration for this post. An Astronomer customer asked us about using logfiles, citing Kerry's tweet.

Back when we were living in a world where everything happened on the server, and there was only one server and service behind the application, this was a good solution. That world is dying, though. Raw logfiles are becoming less and less useful as a source for user event data, as more user interactions can occur in the web browser or app without triggering a backend event.

There are solutions to aggregate logfiles into a central, accessible location. I'd argue this is just another variation of option #3.

---

## Where are you with your product?

There are **a lot more options** available than are discussed above.

We're considering offering a service to help you sort through all the options, and optimize the value you get in exchange for your investment (time and money).

Should we? [We'd love to hear your thoughts](mailto:hey@astronomer.io).
