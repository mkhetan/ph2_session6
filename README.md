# ph2_session6
Phase2 Session6 assignment (Q Learning)

__init__

QValues is initialized as an object of class Counter which is an extension to python dictionary.
It will be used to hold QValues of state and action pair as and when those states and actions are taken.
If a particular state and action does not exist yet, its QValue will be 0.  
 
getQValue

Return the current Q value of the requested state and action Q(s,a).

#Since it uses the QValues which is a Counter dictionary, it will automatically returns
#0 if the state and action do not exist yet.



computeValueFromQValue(inputState)

#This function is required to return the maximum of all the Q(s,a) in a state for all the actions in that state

 return maximum_of (Q( giveState ,action1), Q( givenState, action2), Q(givenState, action3) ...) otherwise 0
 
computeActionFromQValues

# Return the best action. Best action is the action with max Q(s,a) in that state
  
  get the value of this state s ( this is the max value of amongst all the actions )
  Get Q(s,a) of all the legal a in this state state
  The action a for which the Q(s, a) matches the best value (got in the 1st step) is the best action
  
getAction

    Return a random legal action sometimes ( based on a predefined percentage ) (to create a stochastic environment)
	All other times, return the best action (based on max Qvalue in that state)
	
update

newQVal = oldQVal + LearningRate*(Temporal Difference)

Temporal_Difference = reward(s,a) + gamma*max(Q(s',a')) - oldQval

newQval = oldQVal + LearningRate*( reward(s,a) + gamma*max(Q(s',a')) - oldQval )
newQval = oldQVal + LearningRate*reward(s,a) + LearningRate*gamma*max(Q(s',a')) - LearningRate*oldQval

or it can be represented as:

newQval = (1 - LearningRate)*oldQval + LearningRate*(reward(s,a) + gamma*(max(Q(s',a'))))
