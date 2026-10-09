
## Context and research question

The impact of global warming is undeniable, with rapid, widespread changes in atmosphere, ocean, biosphere, and cryosphere. A major contributor to global carbon emissions is the textiles industry, which generates 8-10% of annual global carbon emissions through apparel and footwear industries, projected to account for around 25% of the carbon budget by 2050.

To combat these effects, the European Green Deal was approved in 2020 and made legally binding through the European Climate Law. The resulting Ecodesign for Sustainable Products Regulation (ESPR) introduces the Digital Product Passport (DPP), mandating that information pertaining to almost all created and imported products is documented.

The future implementation of DPPs is expected to face several challenges, notably the physical
medium used to access the information. Physical carriers such as QR codes and RFID chips are
unreliable, as they are easily damaged or removed by consumers. Without a physical tag, the
industry requires alternative, tagless methods to characterise a textile. Established techniques
such as spectral and chemical analysis may offer an alternative, but no single technique provides a complete picture, and combining multiple test methods introduces a new challenge: synthesizing their separate findings into one textile characterisation. Currently, no system exists that addresses this gap in a way that is accessible to textile specialists under real-world conditions.

To address this gap, the following research question was posed:

> "How can an AI-supported decision system using multimodal tests contribute to the characterisation of fibres while handling uncertainty and supporting textile specialists in a Digital Product Passport context?"

## Requirements

|ID|Requirement|MoSCoW|
|---|---|---|
|FR1|The system combines multiple test modalities to output fabric class characterizations.|Must have|
|FR2|The system continues to produce an output when one or more modalities are missing.|Must have|
|FR3|The decision mechanism weights modalities by test confidence.|Must have|
|FR4|The system suggests additional tests when current evidence is insufficient and makes clear that the result is not conclusive.|Should have|
|FR5|The system flags tests that are likely unreliable for the current sample and recommends a retest or an alternative test when appropriate.|Should have|
|FR6|The system includes a CNN that processes microscopy images to classify textiles by fibre type.|Must have|
|NF1|The system presents information transparently so users can inspect how outputs were produced.|Must have|
|NF2|The system communicates uncertainty in each estimation in a form that is understandable to users.|Must have|
|E1|The system avoids overconfident autonomous claims and instead acts as a decision support system.|Must have|
|E2|The system requires a human-in-the-loop to interpret the characterization.|Must have|

## Designs

### Option 1

![[design_1.png]]

### Option 2

![[design_2.png]]

## Happy flow

Happy flow for any test

![[happy_flow_1.excalidraw]]

Happy flow for the CNN

![[Happy flow - composition.excalidraw]]

## AI breakdown

There doesn't seem to be a single answer to how many mistakes can be made. It really depends on the user.

For example:
1) A distributor, while it would be bad to make mistakes, it has relatively little impact on their overall process.
2) For a recycling system making mistakes can ruin entire batches.

| In                   | Task                                                              | Out                                            | Possible mistakes                                                                                             | Impact of mistakes | % of mistakes still valuable | Possible solutions                                                                                                                                                                    |
| -------------------- | ----------------------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------ | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fabric test          | Find fabric tests that have similar results.                      | Similarity scores for that specific test type. | There are no similar items.<br><br>Items that are similar are not correct.                                    | Low.               | ?                            | Show uncertainty to the user.<br><br>When there are not enough similar items, tell the user to redo the test.                                                                         |
| Several fabric tests | Combine the per-test similarity scores into one characterization. | Combined characterization.                     | Combining the tests leads to a worse overall characterization.                                                | Medium.            | ?                            | Make sure the user understands it's a characterization, not a classification. Responsibility lies with them.                                                                          |
| Failed fabric test   | Make sure the user gets notified that there was something wrong.  | Error message and suggestion to redo the test. | Test gets classified as wrong but has been performed well.<br><br>Test gets classified as correct but is not. | Medium.            | ?                            | Most fabric characterization tests rely on some standard. Always remind the user to abide by the standards.<br><br>Give the user control over whether the results should be included. |

## Error flow

![[Error flow.excalidraw]]

## Test Plan

Testing is done with the Fashion & Technology lab and focuses on the happy flow of the application. Since Responsible IT, the technical project lead, holds primary interest in the back-end process, the testing scope reflects this emphasis.

Two overlapping happy flows are evaluated, namely the one involving a CNN. During testing, the participant uploads an image of a fabric and receives a characterization based on a single test result. If multiple test results are available for the same fabric, the system produces a combined characterization.

The participant is asked to think aloud throughout the process. Notes and observations are written down where the application performs well, where confusion arises, and what features may be missing. Following the session, the participant is interviewed with the questions below:

- Was the entire process understandable?
- Is there anything important missing?
- Does the characterization make sense? Is it correct?
- Were you able to find all of the buttons and pages?
- Do you trust the characterization? Why or why not?
- If the system expressed uncertainty, was that communicated clearly enough?
- If multiple tests were combined, did the final result feel justified?
- How would this fit into your existing workflow?
- Do you have any additional comments?