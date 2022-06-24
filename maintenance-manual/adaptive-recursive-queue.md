# Adaptive Recursive Queue

Adaptive Recursive Queue Engine. This is required only for outbound requests from product.

### What is the idea of making this?

The idea is to make a system which can retry requests going out from the Signzy system. For example

1. IndusInd - Underlying APIs failure
2. Onboarding Engine - Callback URL is not working when the callback was initiated after verification engine completed processing

#### Why not a retrial every 10 seconds, upto 10 retries?

There are two problems with this

1. It will not work in cases where the external system was down for more than 10 x 10 = 100 time units
2. Say a request will get retried after 10 seconds when it failed, so the system is obliged to try the same request every 10 seconds for the same as long as it continues to fail.
   1. In a scenario where say we are getting 1000 requests per seconds and say our system.
   2. And our system asks the database for data to work on every 100 millisecond, then we will take 10 tasks in 1 second and 100 tasks in 10 seconds. In this case we can only take 100 tasks = 10 x 10
   3. Say all the 100 are failing, so unless all of them have expired we can’t take the 101th request.

### Tech specifications

We create a decay mechanism in the elements entered in our system.

The idea is to try after more time as an API endpoint fails more and more. We will do it using fibonacci series.

1. Nth element will be called after Fn seconds, where Fn  is nth fibonacci number.
2. The next time is to be calculated using
3. For example
   * Request 1 at 2 seconds after creation
   * Request 2 at 3 seconds after creation
   * Request 3 at 5 seconds after creation
   * Request 4 at 8 seconds after creation
   * Request 5 at 13 seconds after creation
   * Request 6 at 21 seconds after creation
   * Request 7 at 34 seconds after creation
   * Request 8 at 55 seconds after creation
   * Request 9 at 89 seconds after creation
   * Request 10 at 144 seconds after creation
   * Request 11 at 233 seconds after creation
   * Request 12 at 377 seconds after creation
   * Request 13 at 610 seconds after creation
   * Request 14 at 987 seconds after creation
   * Request 15 at 1597 seconds after creation
   * Request 16 at 2584 seconds after creation
   * Request 17 at 4181 seconds after creation
   * Request 18 at 6765 seconds after creation
   * Request 19 at 10946 seconds after creation
   * Request 20 at 17711 seconds after creation
   * Request 21 at 28657 seconds after creation
   * Request 22 at 46368 seconds after creation
   * Request 23 at 75025 seconds after creation
   * Request 24 at 121393 seconds after creation
   * Request 25 at 196418 seconds after creation
   * ……….. And so forth

We will use a key value database.

## Setting retrial criteria

The retrial criteria can be found at the location. The regexes that you put in here will all be checked and only upon getting success for each of the regex - i.e. on successful match of each of the regex in the response body of that particular API.

Below screenshot gives an indication on how to make the change with an example for each of the retrial APIs.

![](<../.gitbook/assets/image (2).png>)

