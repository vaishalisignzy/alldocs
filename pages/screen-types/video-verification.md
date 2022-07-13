# Video Verification

The Video verification page screen is used to verify that the documents uploaded belong to the same person who is onboarding the journey. For this, we are required to choose a reference page of a document uploaded by the merchant containing his image, which the Video Verification API will use as a reference to perform the face matching.

On choosing the reference page, the following happens&#x20;

* The Video Verification API requires us to select the image variables from the page which will be included as parameters for the Face match.&#x20;
* Now, that image will be compared to the video, and we will be getting a score based on that comparison in the backops portal.

![](https://lh6.googleusercontent.com/8xNtP75Wia4ZzPtb3Y1YiHc\_6c1DDtmD9yA2djBhMMa6anhdSCXEg5PYCLeid7hNtP\_Asj67-dV8dVeIJTlcqeQuZ0QBs\_jBE-8N4\_83gDpMr\_At\_rIN\_Pzlwu7R--v9xOLvt7Cu3oQPJTFN6g)

Steps for customizing the video verification page:&#x20;

1. Select screen type as Video verification&#x20;
2. Choose a page containing an image for video verification&#x20;
3. Select the correct variable name containing the image&#x20;
4. Verification by Gesture option
   * Blink&#x20;
   * Smile&#x20;
   * Yawn&#x20;
   * Left&#x20;
   * Right

**So how it works is**, that we need to select single or multiple gestures. For instance, if we select Blink and Yawn and set the Sequence length to five, then the merchant must blink and yawn in sequence five times to complete the verification.&#x20;

* OTP Required option Under verification by gesture, one more option to complete the verification is by enabling OTP, where we can set a custom time limit for the video to be recorded, the video time limit could be set between 5-30 seconds.

While onboarding, a random six-digit number will be displayed to the merchant that needs          to be read while on video, for the merchant's authenticity to be verified.  &#x20;



**Additional Options**&#x20;

1. Hide top logo&#x20;
2. Hide bottom logo&#x20;
3. ID verification required       &#x20;

### Use Cases:
