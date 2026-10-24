
# Engineering Challenges & Solutions — Hikrobot VisionMaster

**Project:** Industrial Machine Vision & Automated Inspection  
**Organization:** ABW Technologies, Malaysia  
**Role:** R&D Software Intern — Machine Vision  
**Year:** 2026  
**Platform:** Hikrobot VisionMaster

> **Confidentiality Notice:** The following case studies are generalized from my industrial training experience. They describe engineering challenges and troubleshooting methods without revealing customer information, proprietary inspection recipes, production images, machine configurations, or confidential performance data.

## Overview

Developing an industrial inspection solution involves more than configuring image-processing tools. A solution must also remain reliable when image conditions, component positions, and inspection results vary.

During my internship, I developed and optimized VisionMaster inspection recipes and investigated unexpected inspection behavior during testing and on-site validation.

The following case studies highlight four important engineering challenges and the approaches I used to investigate them.

---

## Challenge 1 — ROI Positioning and Component Variation

### Problem

An inspection region configured for one image may not remain correctly positioned when the inspected component moves or changes orientation.

A fixed Region of Interest (ROI) can therefore evaluate the wrong image area, potentially causing inconsistent detection results.

### Investigation

When an inspection produced unexpected results, I examined:

- Whether the required feature was visible in the acquired image.
- Whether the ROI covered the intended inspection area.
- Whether the component position differed from the reference image.
- Whether positioning or alignment operations were working correctly.
- Whether the inspection tool received the expected image region.

### Engineering Approach

I worked with VisionMaster positioning, matching, fixture, and ROI configuration tools to maintain the relationship between reference features and inspection regions.

Where appropriate, I refined the reference positioning and adjusted inspection regions before repeating the tests.

### Key Learning

Reliable inspection depends on evaluating the correct feature consistently.

Improving positioning and ROI behavior can be as important as adjusting the defect-detection tool itself.

---

## Challenge 2 — False Calls and Escapes

### Problem

An industrial inspection solution must distinguish acceptable conditions from defects.

Two important errors are:

- **False call:** An acceptable condition is incorrectly rejected.
- **Escape:** A defective condition is incorrectly accepted.

An overly sensitive configuration may increase false calls, while an insufficiently sensitive configuration may allow defects to escape.

### Investigation

When an incorrect inspection result occurred, I reviewed:

1. The original image and relevant visual feature.
2. The ROI and positioning behavior.
3. The inspection tool's intermediate output.
4. Configured thresholds and decision conditions.
5. Differences between acceptable and defective samples.
6. Whether the error was consistent or occurred only under certain conditions.

### Engineering Approach

I adjusted inspection parameters and ROIs based on observed errors, then repeated testing using representative samples.

The objective was to improve detection consistency without relying on a single successful inspection result.

### Validation

My internship presentation documented a selected validation test that achieved zero false calls and zero escapes under the tested conditions.

This was a **specific validation observation**, not evidence of zero errors across all production conditions.

Exact customer, machine, sample, and inspection details are intentionally excluded from this public case study.

### Key Learning

Inspection optimization requires balancing defect sensitivity with tolerance for acceptable variation.

Repeated testing and error analysis are essential before considering a recipe ready for integration.

---

## Challenge 3 — Correct Tool Output but Incorrect Final Decision

### Problem

A vision tool may correctly detect a feature or return an expected measurement, while the overall inspection still produces an incorrect OK/NG result.

This can happen when the issue is not the detection algorithm itself, but the surrounding workflow.

### Investigation

During inspection testing, I encountered situations where individual tool outputs were correct but the final inspection result was inconsistent.

To investigate, I traced the inspection sequence and checked:

- Intermediate outputs from the relevant tools.
- Data connections between inspection operations.
- Decision conditions and logical comparisons.
- Whether the expected result reached the final decision stage.
- Whether the workflow was evaluating the intended values.

### Engineering Approach

Instead of immediately changing the detection parameters, I investigated the data flow and decision logic.

I reviewed the relationship between individual inspection results and the combined OK/NG decision, corrected the relevant configuration where necessary, and repeated testing.

### Key Learning

A correct algorithm output does not guarantee a correct system-level result.

Reliable machine vision requires validating both individual inspection tools and the logic connecting them.

This experience strengthened my ability to troubleshoot complete workflows rather than isolated modules.

---

## Challenge 4 — Image Quality and Inspection Consistency

### Problem

Inspection results can vary when the acquired image does not consistently represent the feature being evaluated.

Factors such as lighting, exposure, focus, contrast, and visual variation can influence inspection performance.

### Investigation

Before assuming that an unexpected result was caused by the inspection algorithm, I examined the acquired image.

I considered:

- Whether the relevant feature was clearly visible.
- Whether lighting or contrast affected feature visibility.
- Whether the image was properly focused.
- Whether the inspection region contained sufficient information.
- Whether preprocessing could help isolate the required feature.

### Engineering Approach

I evaluated image acquisition conditions and applied or adjusted appropriate preprocessing and inspection settings when needed.

I then repeated the inspection to determine whether the changes improved consistency under the tested conditions.

### Key Learning

Image quality is a fundamental part of machine vision engineering.

A well-configured inspection tool cannot compensate reliably for every acquisition problem.

Troubleshooting should therefore begin with the input image before moving to more complex algorithm adjustments.

---

## My Troubleshooting Method

Throughout my internship, I developed a systematic approach to investigating inspection problems:

**Observe → Reproduce → Isolate → Investigate → Correct → Retest → Verify**

| Stage | Engineering Action |
| --- | --- |
| Observe | Identify the unexpected inspection behavior |
| Reproduce | Determine the conditions under which the issue occurs |
| Isolate | Identify the relevant image, tool, ROI, or workflow stage |
| Investigate | Examine intermediate outputs, parameters, and decision logic |
| Correct | Make a targeted configuration or workflow adjustment |
| Retest | Repeat the inspection using representative conditions |
| Verify | Evaluate whether the correction addresses the original issue |

This approach helped me avoid making arbitrary parameter changes without understanding the source of a problem.

---

## Engineering Skills Demonstrated

These experiences strengthened my practical skills in:

- Industrial machine vision troubleshooting.
- ROI configuration, fixture, and alignment.
- Rule-based and AI-assisted inspection development.
- Image acquisition and preprocessing.
- Defect-detection parameter optimization.
- False-call and escape analysis.
- Inspection workflow debugging.
- Intermediate-result and decision-logic validation.
- Iterative testing and on-site problem-solving.

## Final Reflection

One of the most important lessons from my industrial training was that **building an inspection solution and making it reliable are two different engineering challenges**.

A workflow may function correctly on an initial sample but require further investigation when component positioning, image appearance, or inspection conditions change.

Working through these challenges helped me become more systematic in debugging, more careful when interpreting inspection results, and more confident in developing complete VisionMaster solutions.

---

## Related Documentation

- [VisionMaster Overview](overview.md)
- [Inspection Workflows](inspection-workflows.md)
- [Software Engineering Challenges](../engineering-challenges.md)
- [System Architecture](../architecture.md)

> **Evidence Boundary:** These case studies describe documented internship activities and generalized engineering approaches. They do not disclose proprietary implementations or claim universal inspection accuracy, independently verified production performance, or sole ownership of the broader industrial system.
