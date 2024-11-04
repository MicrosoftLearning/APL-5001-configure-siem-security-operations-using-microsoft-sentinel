---
lab:
    title: 'Exercise 4 - Mitigate threats using Microsoft Defender for Cloud'
    module: 'Explore Governance Rules'
---

# Exercise 4 - Explore Governance Rules

## Lab scenario

Governance rules can identify resources that require remediation according to specific recommendations or severities. Microsoft Defender for Cloud continuously assesses your hybrid and multi-cloud workloads and provides you with recommendations to harden your assets and enhance your security posture. Central security teams often experience challenges when driving the personnel within their organizations to implement recommendations. The rule assigns an owner and due date to ensure the recommendations are handled. Many governance rules can apply to the same recommendations, so the rule with a lower priority value is the one that assigns the owner and due date. Governance rules will help:

- Security teams: Set accountability for recommendations, track their progress, and drive resource owners to action with notification capabilities.
- Workload owners: Focus on the specific recommendations that require their attention. They'll also be able to delegate recommendations to others or set expectations for when the recommendations will be implemented.

### Task 1: Assign Governance Rule

1. Under Cloud Security, select Security posture from the left menu items.

1. The Secure score defaults to the Azure environment.

1. Under the Environment tab, select View recommendations > link.

1. Select Add filter and then select Resource type.

1. Select **Virtual machine** checkbox and then select the **Apply** button.

1. Select any recommendation where the status isn’t “Completed”.

1. Review the recommendation and in the Take action tab scroll down to Delegate and select Assign owner & set due date.

1. In the Create assignment window, leave Type set to Defender for Cloud and expand the Assignment details.

1. In the Set owner Email address box, type in your admin email. Hint: You can copy it from the instructions in the Resources tab.

1. Explore the Set remediation timeframe and Set email notifications options and select Create.

    >**Note:** If you see the error Failed to create requested assignments, try again later.

1. Close the recommendation page by selecting the ‘X’ on the upper right of the window.

## You have completed the lab
