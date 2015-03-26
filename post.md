When you're launching the initial, MVP version of your product, user analytics is pretty simple. Usually you'll setup [Google Analytics](http://www.google.com/analytics/), and add a well-known, all-in-one user analytics tool like [Mixpanel](https://mixpanel.com/), [KISSmetrics](https://www.kissmetrics.com/), [Popcorn Metrics](http://www.popcornmetrics.com/), [Flurry](http://www.flurry.com/), [Heap](https://heapanalytics.com/), or [Churnbee](https://churnbee.com). All good tools.

You won't have a good plan for what you want to measure, so you just make sure that signups are making it into the system, and maybe a few other events, for good measure.

And since you don't really have much to look at yet, or any historical context to compare your numbers with, you just forget about metrics for a while. You're on the free tier — so no worries — back to building product.

At some point, though, you'll get an uneasy feeling that you're not really using the full power of the tool, especially once you outgrow the free tier, and start spending real money. Around the same time, you'll also begin to have questions that aren't answerable by these all-in-one tools.

Then you get a question like this:

> "How's your weekly active user retention look?" - a sophisticated investor 

Shit just got real. Time to get on your A game.

You then enter the crazy world of modern analytics, where tools come in all shapes, sizes, and costs; the options are daunting. 

---

## Option 1: Move to an upstream all-in-one tool

I hear good things about [RJMetrics](https://rjmetrics.com/), though I don't have any direct experience. It might be a good option for you, if you want to minimize complexity. There are probably other options. I'm personally not a big fan of this option, so onto the next one...

---

## Option 2: Add-ons

These tools provide a nice layer of information with minimal effort, and without having to ship your data off to them.

Engagement/Churn Prediction — [Preact](http://www.preact.com/), [Framed Data](https://www.framed.io/) — sits on top of [Salesforce](http://www.salesforce.com/), [Desk.com](http://www.desk.com/), [Mixpanel](https://mixpanel.com/), etc.

SaaS metrics — [ChartMogul](https://chartmogul.com/), [BareMetrics](https://baremetrics.com/) — sits on top of Stripe, etc.

---

## Option 3: Establishing your own events datawarehouse

The bulk of this post is focused on this option, because you will eventually need to get here — may as well get the party started.

There's a good chance you're already behind the 8-ball here. It's quite common to be missing critical data already, rendering your historical data incompatible with the schema you want to use going forward. This can be a real bummer, but it's better to blow this landmine up as early as possible.

### Data Collection

If you're still light on internal data science capability, and event volumes aren't too high, we think [Keen IO](https://keen.io/) is a great option for your first user events datawarehouse. It has very usable tools to get data both in and out, and the pricing is fair.

If you're already at high event volumes, and have people with good SQL-fu on your team, [Snowplow Analytics](http://snowplowanalytics.com/) is a powerful option that results in a clean, tidy datawarehouse in [Amazon Redshift](http://aws.amazon.com/redshift/), which is accessed via a subset of PostgresSQL commands, and is a gateway into the world of higher-end data processing and analysis.

[Segment](https://segment.com/) can [store your user events](https://segment.com/redshift) in Amazon Redshift as well, though the service is still limitedly available, and somewhat expensive.

### Analysis and visualization

If you have a data scientist (or someone who can play one on TV) and your own datawarehouse, you can leverage an impressive collection of cloud-based analysis tools, including [Mode](https://modeanalytics.com/), [Looker](http://www.looker.com/), [Chartio](https://chartio.com/), and [Datahero](https://datahero.com/) (in addition to traditional tools like [R](http://www.r-project.org/) and [Tableau](http://www.tableau.com/)).

If you're light in the data science department, you can look take advantage of our [USERcycle recipes](https://usercycle.com/recipes) which connect directly to your datawarehouse, and provide a end-to-end analysis and visualization, inspired by the best practices of world-class product owners.

---

## Option 4: Logfile analysis 

A [tweet by Kerry Rodden](https://twitter.com/kerryrodden/status/579397570100785152) was the inspiration for this post. A USERcycle customer asked us about using logfiles, citing Kerry's tweet.

Back when we were living in a world where everything happened on the server, and there was only one server and service behind the application, this was a good solution. That world is dying, though. Raw logfiles are becoming less and less useful as a source for user event data, as more user interactions can occur in the web browser or app without triggering a backend event.

There are solutions to aggregate logfiles into a central, accessible location. I'd argue this is just another variation of option #3.

---

## Need help?

There are a lot more options available than we've discussed.

We're considering building a service offering to help owners of growing products sort through the options and optimize their effort and expense.

[Drop us an email if you think we should go for it (or not)](mailto:hey@usercycle.com).
