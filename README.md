# Strapi-Blind-SSRF
Blind SSRF vulnerability allowing internal resource enumeration through DNS requests, impacting Strapi v5.23.0

Repetition：
<img width="2400" height="1530" alt="1" src="https://github.com/user-attachments/assets/2c732857-ecce-4af7-a272-acb696048ca7" />

path：settings - Webhooks - Create new webhook
<img width="2556" height="1539" alt="2" src="https://github.com/user-attachments/assets/c5083f20-21b0-4dbf-95da-56f05e26e606" />

First of all, let's input the URL http://127.0.0.1:80 into the URL field, and click "Save"
<img width="2559" height="1511" alt="3" src="https://github.com/user-attachments/assets/a2e4035d-5361-47f7-9085-0703ff225c0c" />
<img width="2541" height="1326" alt="4" src="https://github.com/user-attachments/assets/c92d7cc0-4677-4550-9d1f-88b5a27907db" />

Next, use the "Trigger" function and use Burp Suite to capture the request / response
I have Apache running on my computer with port 80 open. Testing confirms that when the server port is accessible, it responds with a 404.

<img width="972" height="135" alt="8" src="https://github.com/user-attachments/assets/2ab9d282-287b-4891-9116-bf05db0cdc58" />
<img width="2076" height="735" alt="5" src="https://github.com/user-attachments/assets/4818a7ca-f330-4447-b447-b5984a8a06ff" />
<img width="2067" height="698" alt="1" src="https://github.com/user-attachments/assets/a5557932-db7b-49fa-8470-abcdbea29b70" />



When testing port 81, a closed port results in a 500 response
<img width="843" height="135" alt="9" src="https://github.com/user-attachments/assets/2e5ee925-30f0-41e3-b380-0a34c06de837" />
<img width="2538" height="1431" alt="10" src="https://github.com/user-attachments/assets/f28c837b-3260-4e8c-b102-e0e409ab2d7a" />
<img width="2067" height="795" alt="11" src="https://github.com/user-attachments/assets/fca3a6ba-f64b-4e42-99f8-2fac5f3661b3" />
<img width="2082" height="789" alt="12" src="https://github.com/user-attachments/assets/eade2f4b-3ff2-4f4d-be57-a09433df2a3a" />

dns test：
<img width="1959" height="1077" alt="1" src="https://github.com/user-attachments/assets/191387f5-52dc-4bd3-8c51-6af1947dbd95" />
<img width="2061" height="945" alt="2" src="https://github.com/user-attachments/assets/30e4bda5-a072-48f8-9e66-525415c73a71" />
<img width="2088" height="954" alt="3" src="https://github.com/user-attachments/assets/1d63793c-c780-4d3a-a3e9-8377dcaddef8" />
<img width="1848" height="1017" alt="4" src="https://github.com/user-attachments/assets/d5dfe844-ad49-4c87-a7ee-955d7931a7ff" />

Testing DNS using other platforms.：
<img width="2195" height="711" alt="1" src="https://github.com/user-attachments/assets/be984f53-20bf-4d7b-aaa3-62952205b721" />
<img width="2058" height="837" alt="2" src="https://github.com/user-attachments/assets/a00042ff-e101-429c-a1d1-1364abae27fe" />
<img width="2067" height="780" alt="3" src="https://github.com/user-attachments/assets/d6ab8830-3859-4e0b-ac5d-e218a7badae5" />
<img width="2048" height="1274" alt="4" src="https://github.com/user-attachments/assets/00858bdf-1f4f-4547-8062-e3c48b098134" />
<img width="1959" height="1314" alt="5" src="https://github.com/user-attachments/assets/db5e84c2-3883-4194-b4f8-da1af53694d4" />


