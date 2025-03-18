# From MVP to V1: Adjusting Development Strategies


### How should software be built?

It depends.

There isn't a single "correct" way to build software. An early stage startup might focus on speed over maintainability, because they're looking to find Product-Market Fit (PMF). A scale-up which has found PMF might focus instead on maintaining engineering velocity. Both are solutions to two completely different equations.

If we broadly group development "modes" into two buckets we can come up with the following buckets:

- MVP
- V1

MVP is everything before Product-Market Fit. V1 is after Product-Market Fit. Let's define what Product-Market Fit is.

### Product Market Fit (PMF)

According to [Wikipedia](https://en.wikipedia.org/wiki/Product-market_fit):

> Product-market fit, also known as product/market fit, is the degree to which a product satisfies a strong market demand.

To rephrase this, it means you've proven that customers will pay for what you are building. 

[How to identify if you product has found Product-Market Fit](https://stripe.com/en-sg/resources/more/what-is-product-market-fit-what-startups-need-to-know) is beyond the scope of this post and is best left up to the product team to debate.

### Pre-product market fit

At this point, speed is everything. There are a million and one failed startups that have not found PMF. The first objective of a startup is to achieve product-market fit.

What do you not do here?

- Design highly scalable architecture
- Automate repetitive processes
- Refactor and clean up tech debt
- Write unit tests to make it easy to refactor and extend functionality
- Write code that is easy to unit test

A few caveats:
- If it's faster to write a unit test to verify some complex logic is correct, it's okay to do so.
- If you write any tests at all, integration tests and end-to-end tests have the highest return on investment here.

The goal is to validate your product hypothesis as quickly as possible. If you fail fast and fail cheaply, this means you have more opportunities to pivot and try different ideas.

### Post Product Market Fit

Congrats, you've found PMF. Customers are banging down your door to buy your product. Now you can build everything for real. You know the crappy MVP that's held together by scotch tape and hacky workarounds? You can now build your V1 the "right way". This doesn't mean over-engineering the living daylight out of your system. It means selecting the minimal set of practices which allow you to maintain your engineering quality and velocity.

Often companies will build on top of what already exists and evolve the MVP. This creates competing incentives because when building an MVP, any corner that can be cut should be cut. If you know you'll throw away the MVP, it removes any unnecessary constraints and also simplifies the solution space for the MVP and the V1.

A few considerations:
- In the process of building an MVP, you will have discovered better abstractions and models of the problem space.
- For a V1, you can start to think about how to architect your system and development process to increase development velocity and feature quality.

### Conclusion

Hopefully, I've helped clarify that there's no single "correct" way to build software. What's right for one team might be completely wrong for another. The optimal approach depends on the context around which the software is written. By recognizing that each company and team is a different equation to solve for, you can tailor your software-engineering practices to suit the unique constraints and goals of each organization.













