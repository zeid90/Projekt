system assignment1_7 {
    declarations {
   	 indexed Period, Deadline, CompTime, RespTime;
   	 priority Priovar;    
   	 tasks t1, t2, t3;
    }
    initialise{
   	 CompTime[t1] = 2;
   	 CompTime[t2] = 4;
   	 CompTime[t3] = 10;

   	 Period[t1] = 10;
   	 Period[t2] = 15;
   	 Period[t3] = 35;

   	 Deadline[t1] = 10;
   	 Deadline[t2] = 15;
   	 Deadline[t3] = 35;

   	 Priovar[t1] = 1;
   	 Priovar[t2] = 2;
   	 Priovar[t3] = 3;
    }
    formulas{
   	 RespTime[i] = CompTime[i] +  sigma(hp,ceiling(RespTime[i]/Period[j])*CompTime[j]);
    }
}
