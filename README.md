global class OpportunityCheckTheBox implements Database.Batchable<sObject> {
    
    global Database.QueryLocator start(Database.BatchableContext BC){
     
        String query = 'SELECT Id,Name,Amount,ExpectedRevenue,Private FROM Opportunity where Private = True AND Amount != ExpectedRevenue ';
        return Database.getQueryLocator(query);
    }
   
    global void execute (Database.BatchableContext bc, List<Opportunity> optyList){
        
        for
           (Opportunity Opty :optyList ){
             opty.Amount != opty.ExpectedRevenue;
             Private = True;  
            }
        update opty.Private;
    }
    
        
    global void finish (Database.BatchableContext Bc){       
    }
    }
