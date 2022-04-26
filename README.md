functionminimax(node,depth,alpha,beta,maximizingPlayer)is
ifdepth==0ornodeisaterminalnodethen
returnstaticevaluationofnode
ifMaximizingPlayerthen //forMaximizerPlayer
maxEva=-infinity
foreachchildofnodedo
eva=minimax(child,depth-1,alpha,beta,False)
maxEva=max(maxEva,eva)
alpha=max(alpha,maxEva)
ifbeta<=alpha
break
returnmaxEva
else //forMinimizerplayer
minEva=+infinity
foreachchildofnodedo
eva=minimax(child,depth-1,alpha,beta,true)
minEva=min(minEva,eva)
beta=min(beta,eva)
ifbeta<=alpha
break
returnminEva
