# Research

## Policy and DPP Context

I first looked at the policy context behind Digital Product Passports. The research covered the European Green Deal, the Circular Economy Action Plan, the Ecodesign for Sustainable Products Regulation, and the idea of a Digital Product Passport.

Evidence:

- [Digital Product Passport note](../rapport/research/Digital%20Product%20Passport.md)
- [Ecodesign for Sustainable Products Regulation note](../rapport/research/Ecodesign%20for%20Sustainable%20Products%20Regulation.md)
- [Circular Economy Action Plan note](../rapport/research/Circular%20Economy%20Action%20Plan.md)
- [European Green Deal note](../rapport/research/European%20Green%20deal.md)

## Textile Characterisation

I also researched textile structure and textile characterisation methods. The main point was to understand the chain from fibre to yarn, fabric, and garment.

This research led to a fabric-level scope. A finished garment can contain multiple materials and components, and a fabric sample is a simpler material for testing composition. The research into chemical tests and spectroscopy also showed that no single test gives the full picture, because different tests measure different properties.

Evidence:

- [Fiber note](../rapport/research/Fiber.md)
- [Chemical Tests note](../rapport/research/Chemical%20Tests.md)
- [FT-IR Spectroscopy note](../rapport/research/FT-IR%20Spectroscopy.md)

## Data and AI Direction

The technical research focused on what kind of data and AI approach could support textile characterisation. The final thesis direction uses the NIR-SORT dataset as the dataset because it contains known-provenance fabrics with image and spectroscopy data.

The research also shaped the model direction. Image data can be represented through CNN embeddings, while spectra can be compared as molecular measurement vectors. This made it possible to compare image-only, spectra-only, and combined evidence.

Evidence:

- [Research folder](../rapport/research)

## Decision Support and Uncertainty

The system direction also depends on how test outputs are combined and explained. I researched similarity scores, test weighting, and missing tests.

MCDM and the Best-Worst Method became relevant because different tests do not always have the same importance. The project therefore separates test weighting from confidence and keeps individual test outputs visible, so a user can see where the result comes from.

Evidence:

- [Design review note](../rapport/research/Design%20review.md)

## Research Choices That Followed

The research led to these main project choices:

- Focus on fabric-level characterisation.
- Use multimodal evidence instead of relying on one test.
- Use late fusion so test outputs can be inspected separately before they are combined.
- Use NIR-SORT as the first dataset for prototype evaluation.
- Represent microscopy images with CNN embeddings.
- Use BWM weights for test importance.
- Keep human judgement in the loop.

## Evidence

The main research is written in the thesis.

- [Research folder](../rapport/research)
- [Design review note](../rapport/research/Design%20review.md)
