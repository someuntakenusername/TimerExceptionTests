Tasks to answer in your own README.md that you submit on Canvas:

1.  See logger.log, why is it different from the log to console?
	1.	Only INFO level statements are recorded in the console
1.  Where does this line come from? FINER org.junit.jupiter.engine.execution.ConditionEvaluator logResult Evaluation of condition [org.junit.jupiter.engine.extension.DisabledCondition] resulted in: ConditionEvaluationResult [enabled = true, reason = '@Disabled is not present']
	1. The failed Timer Test
1.  What does Assertions.assertThrows do?
	1. Checks if the lambda expression throws the specified exception class and failed the test if no exception meeting the conditions was thrown
1.  See TimerException and there are 3 questions
    1.  What is serialVersionUID and why do we need it? (please read on Internet)
		1. A unique value used to valid the same class is serialized across systems, must be hard-coded or the JVM will auto-generate different values for the same class
    2.  Why do we need to override constructors?
		1. The information leading to the problem needs to be preserved across Exception polymorphism
    3.  Why we did not override other Exception methods?	
		1. The current constructors sufficiently preserve information from the problem
1.  The Timer.java has a static block static {}, what does it do? (determine when called by debugger)
	1. Code executed at the start of the application from the context of the class. Loads and parses the config file for the Logger.
1.  What is README.md file format how is it related to bitbucket? (https://confluence.atlassian.com/bitbucketserver/markdown-syntax-guide-776639995.html)
	1. A plain-text format with simple syntax commonly used to auto display information about Git repos
1.  Why is the test failing? what do we need to change in Timer? (fix that all tests pass and describe the issue)
	1. `NullPointerException` thrown trying to operate with timeNow, which is null
1.  What is the actual issue here, what is the sequence of Exceptions and handlers (debug)
	1. throwing `TimerException` causes the `finally` block to execute prematurely, operating on timeNow which is null and throws a `NullPointerException`
1.  Make a printScreen of your eclipse JUnit5 plugin run (JUnit window at the bottom panel) 
1.  Make a printScreen of your eclipse Maven test run, with console
1.  What category of Exceptions is TimerException and what is NullPointerException
	1. `TimerException` is an `Exception`, `NullPointerException` is a `RuntimeException`
1.  Push the updated/fixed source code to your own repository.