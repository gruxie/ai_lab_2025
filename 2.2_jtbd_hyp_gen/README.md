# Lab 2.2 - JTBD

This lab will diverge from the continuity of the previous labs and focus on how to build a prompt that provides structure to the application of a specific methodology: Tony Ulwick's "Jobs-to-be-Done."  When run, the LLM should generate a list of JTBD, their desired outcomes and sub jobs along with the LLM assessment of which jobs have the most opportunity.

>[!IMPORTANT] This Chain of Thought (CoT) requires the user to supply two inputs under "Assumptions:" 1) the research question and 2) the job performer. These inputs are essential for getting more focused results. When run, the LLM should generate a list of JTBD, their desired outcomes, and sub-jobs along with the LLM assessment of which jobs have the most opportunity.

## Exercise 1: Get an initial analysis
1) Determine your research question and job performer from the list of examples below (bring your own if you like!).  
2) Edit the prompt section under "Assumptions" with the following information (from the examples or your own RQ /job performer):
   - **RQ:** A short, specific research question
   - **Job Performer:** A description of the focal customer or persona
   - **Context:** Include any essential information about the job performer's context. Avoid using language with implied needs since this will bias the prompt's output.
3) Determine which LLM to use (ChatGPT or CoPilot).  Be careful with company and customer data.  If it is general - go ahead and use ChatGPT.  When in doubt, use CoPilot!  
4) Run the prompt!  

## Exercise 2: Add a job
- Follow the steps in Exercise 1 above.  
- Examine the results to determine a main job as an area of focus.
- Instruct the LLM to add another JTBD within the area of focus, of your choosing, and re-run the analysis.

## Exercise 3: Create a discussion guide
- Follow the steps in Exercise 1 above.  
- Make any adjustments you would like to the main jobs or job steps (as you did in Exercise 2).  
- Ask the LLM to generate a discussion guide.

## Materials for this lab

### Prompts:  
[JTBD + Desired outcomes](https://microsoft.sharepoint-df.com/:t:/t/DevDivAIAidedURLab/EQEIXSgPWBJMs3X2-zkLtSABYPW1sTBXDNntIJvCIW-wqg?e=KNkb0w)

### Examples

**Example 1:**  
- **RQ:** What challenges do customers run into when using cloud storage with their personal computers?  
- **Job Performer:** Information workers who create documents.  
- [Worked example in ChatGPT](https://chatgpt.com/share/67d30681-dab4-8004-8ac1-25d99dc492e4)

**Example 2:**  
- **RQ:** What challenges, if any, do developers on ARM development machines encounter when building and deploying software?  
- **Job Performer:** Software developers using ARM client machines for software development.  
- [Worked example in ChatGPT](https://chatgpt.com/share/67d2fb28-4640-8004-ae57-618144b3176e)

**Example 3:**  
- **RQ:** What factors influence consumers' car-buying decisions in response to increased gas prices?  
- **Job Performer:** Car Buyer.

**Example 4:**  
- **RQ:** What are the pain points for customers during the checkout process of an e-commerce platform?  
- **Job Performer:** Online Shopper.

## Recommendations
- It works better when the topic is focused (e.g., 1 RQ, 1 job performer).
- It's easy to unintentionally bias the output with too much outcome-specific context (e.g., avoid using the word "need").
- Run the prompt multiple times—in multiple LLMs if you can—to develop a consensus view.

