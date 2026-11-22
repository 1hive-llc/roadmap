# Keep Honey v1 governing: retire streaming proposals and move to Kleros

*Draft proposal. No vote has been submitted. This document does not contain an executable release.*

I propose we keep Conviction and Decision Voting working instead of following the [full deprecation plan](https://github.com/lkngtn/gardens-v1-deprecation/blob/main/docs/PROPOSAL.md). Retire streaming proposals now, then replace Celeste for new actions with one Kleros court governed by the updated Covenant below. Keep treasury custody and ordinary governance where they are. This is one proposal with two execution steps so the immediate fix doesn’t wait for the court.

**1. Retire streaming proposals first.** Close outstanding FluidProposals streams through an authorized account and verify that the actual flows stopped. Then revoke the pilot’s authority to manage streams or top up its streaming balance. Leave unrelated payment streams and the wrapper’s separate Common Pool permissions in place. This is a permanent retirement of the proposal feature, not a wholesale shutdown of streaming payments.

**2. Launch Kleros and adopt the Covenant together.** Use Decision Voting to append the new Agreement setting with the reviewed Kleros adapter and the exact Covenant text. Returning proposers sign the new terms. Newly registered actions use Kleros; existing actions keep the court and terms they were registered under. This does not revive old Celeste cases or move them to Kleros.

Seed the court with consenting Safe signers as individual **Keepers**; recruiting outside Keepers is not a launch requirement. Open an optimistic registry: unchallenged applications finalize after a review window, and the court hears contested applications and ordinary removals. For the first **90 days**, involuntary removal of a seed Keeper requires a Decision vote. A challenge can still be heard and its findings used in that vote, but neither a ruling nor silence can bypass it. After 90 days the ordinary rules apply. A Keeper cannot hear their own case; failure to form a panel is not a ruling.

**Give the Safe a 90-day recovery mandate.** The Safe can pause new registrations if the court cannot operate, apply a repair to the named Kleros integration, and resume registrations after verifying the repair. A narrowly scoped controller must enforce the allowed settings, targets and expiry onchain. It may correct approved settings or activate a compatible adapter or fallback approved by governance. It cannot make arbitrary calls, move treasury assets, manage permissions, appoint Keepers, decide cases, or change the Covenant. Decision can revoke the mandate early. A fix outside that scope requires a new governance decision.

The pause must not prevent existing votes or cases from progressing, and resuming cannot depend on creating a vote that the pause itself blocks. A new setting does not move actions already bound to Kleros. Before launch, show that those actions, including ones awaiting a challenge, can still reach a valid outcome after repair or through a separate reviewed recovery route.

**Start with the streaming fix.** In parallel, prepare the exact launch payload and rehearse both proposal types, a Keeper membership challenge and appeal, and the recovery path. Don’t hold the first step to debate the second. If rehearsal exposes a problem, revise the launch transaction before it goes live. That is the reason for staging the work, not a reason to delay it.

## How to validate the release

The [court walkthrough](https://1hive.io/previews/honey/) and [protocol source](https://github.com/1hive-llc/honey-protocol) are available now. The walkthrough is illustrative and earlier tests do not validate this launch configuration. Before submission, publish a verification bundle following the [deprecation runbook](https://github.com/lkngtn/gardens-v1-deprecation#readme): a full commit, finalized Gnosis block and hash, pinned tools, current and expected permission snapshots, the exact Covenant bytes and content ID, decoded actions and their hashes, and commands to check the bundle and run an isolated rehearsal without a wallet or private key.

1. **Streaming:** Verify outstanding pilot flows close and its two grants are ineffective. Confirm the wrapper's separate permissions and unrelated payments are unchanged.
2. **Court cutover:** Rehearse signing and both proposal types. Check old and new actions against their saved settings, and show a hearing and appeal through final application of the ruling.
3. **Keeper registry:** Rehearse admission, challenge, appeal, and removal. Show that neither a ruling nor a default can bypass the seed protection, and test expiry and an unavailable panel.
4. **Recovery:** Reproduce pause, scoped repair, and resumption, including an already-bound action. Prove that out-of-scope calls fail and that expiry and early revocation disable the mandate.
5. **Covenant availability:** Pin the approved IPFS content with two independent operators and retain the exact bytes in the release. Independently retrieve and verify both versions and confirm the signing and case interfaces read the right version. Community-operated mirroring is a follow-on milestone, not a launch dependency.

An independent reviewer should reproduce the release hashes and expected state changes before vote submission. Recheck relevant live state before execution. Run and publish the streaming checks as soon as they are ready, without waiting for the court bundle.

## Appendix: proposed 1Hive Community Covenant

### 1. Purpose
1Hive is a community where people and their agents build and steward shared resources. Honey helps the community decide what to fund and reward: useful tools, knowledge, infrastructure and other public or community goods, including the work of maintaining them. We want contributing to be as easy as giving an agent a starting point and enough direction to find useful work. People remain accountable for the authority they delegate. Payment is earned through useful work, not guaranteed by participation.

### 2. How we work together
We commit to an open, welcoming community free from harassment and discrimination. Disagree with ideas and decisions without targeting people. Respect privacy, disclose material conflicts, give people a fair chance to respond, and correct consequential mistakes. These expectations apply to people and to agents acting for them. Do not impersonate others, manufacture support, misrepresent evidence, or overwhelm shared processes with repetitive or low-value submissions.

### 3. Stewardship of shared resources
When asking the community for resources or authority, explain the outcome, who benefits, the cost, who will control the result, and how others can verify it. Disclose materially interdependent requests and their combined cost. Work may be funded in phases when each phase has a separately reviewable outcome. Experiments are welcome: say what is uncertain, limit what the community can lose, and name a condition for stopping or revisiting the work. A good-faith experiment that fails on its merits is different from one that misrepresented its risks or results.

### 4. Practical independence
We favor open-source tools, documented interfaces and portable records so that people and agents can build on the work and keep it going. Hosted services are welcome when they make participation easier or deliver value sooner. The more the community depends on a service, the stronger the case for an exit path. No particular website, company or client speaks for the protocol. We aim to make protocol rules, community resources and prior rulings discoverable and independently verifiable. We pursue that over time and weigh it alongside usefulness, cost and the ability to deliver.

### 5. Disputes and Keeper judgment
Seek a correction or ordinary moderation when that can resolve the problem. Use a formal challenge for a material breach of the Covenant in an action the mechanism covers, or go directly to a challenge when delay could cause harm. State the rule at issue, the relevant facts and the evidence. Give affected parties notice and a chance to answer. Offchain moderation and onchain rulings have different scopes; Keepers decide the question assigned to them and do not invent remedies the mechanism cannot provide.

Apply the Covenant version attached to the action. Weigh the evidence, distinguish facts from inference, and explain how the relevant principles apply. When goals conflict, consider the benefit, who bears the risk, and how hard the choice is to reverse. The question is whether there is a material breach, not whether the Keeper would have made the same decision. An unproven breach is not an endorsement of the proposal. An unavailable panel, failure to respond, and a decision on the merits are different outcomes.

Use comparable prior rulings to develop a body of common law. Follow their reasoning when it applies and explain material differences when it does not. Record the question, applicable Covenant version, outcome and reasons in a discoverable form that respects privacy. Published reasoning can clarify existing principles; neither precedent nor unwritten norms can create a retroactive penalty or silently amend the Covenant.

### 6. Agent-assisted judgment
We expect agents to help throughout a case: gathering evidence, presenting the strongest arguments on both sides, finding comparable rulings, explaining uncertainty and recommending an outcome. A Keeper may rely on that work and adopt its reasoning, but remains responsible for the judgment and personally authorizes the specific ballot. An agent may prepare a ballot for approval, but must not decide or vote independently for a Keeper. Disclose conflicts and don’t adjudicate your own case. Share no more sensitive evidence with tools or the public than the case requires.

### 7. Keeper membership and amendments
Keepers are humans. Publish the eligibility criteria and the procedures for applying, challenging, responding, appealing and leaving. Admission and removal must follow those procedures. Any special launch protection must be public, limited in time and approved through governance; it does not excuse misconduct or give the protected group control over admissions. Keeper eligibility and Safe ownership are separate. Amend the Covenant openly through protocol governance and apply changes prospectively.
