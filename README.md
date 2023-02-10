# Project-backend API Docs
http://group2.exceed19.online
1. get all record in the last hour : [get] http://group2.exceed19.online/record/last_hour
    - return list of
        - x(time) : datetime.datetime
        - y(gas_quantity) : int
2. get all record in the last day : [get] http://group2.exceed19.online/record/last_day
    - return list of
        - x(time) : datetime.datetime
        - y(avg of gas_quantity) : float
2. get last record : [get] http://group2.exceed19.online/record/last
    - return JSON object
        - gas_quantity : int
        - status : enum["SAFE","WARNING","DANGER"]
3. get status of the window : [get] http://group2.exceed19.online/record/command
    - return
        - isOpen : bool[True: เปิด, False: ปิด]
4. create new record : [post] http://group2.exceed19.online/add
    - input JSON object as body
        - gas_quantity : int
        - status : enum["SAFE","WARNING","DANGER"]
    - return JSON object
        - message : "Record created"
5. update status of the window to bool by input : [put] http://group2.exceed19.online/update/{open}
    - input as path
    - return JSON object
        - message : "already set command to {open}"