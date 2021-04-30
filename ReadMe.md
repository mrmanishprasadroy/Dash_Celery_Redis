I have kept Three file for your refrence.


Refer Task.Py
This configuration will send beat to Celery every 60 seconds it can be adjusted to 30 sec or less.
sender.add_periodic_task(
        60,  # seconds
***************
Celery Beat *** -----------------
***************                 |   Refer Task.py for task configuration and Setup_data.py for data processing with redis updation call        
                                | Task is qued and worked upon after reciving the Beat 
                            ***************
                            Celery Task ***
                            ***************
                                    |
                                    | Updation of the calculation in Jason Format  to the Redis database. even if updation failed it will have data to serve the Dash App  
                                    *****************
                                    Redis Database***
                                    *****************
                                            |
                                            | Refer Setup_table.py for the app. 
                                            | No Compution is done here in the call back just retreive the updated data from redis and update time stamp for user info.
                                            ***************
                                            Dash App ***
                                            ***************
