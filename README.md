# Airflow-Soda-Snowflake
Creating a data pipeline in Airflow using snowflake and Soda for quality checks

# REQUIREMENTS

- DOCKER
- AIRFLOW
- ASTRO CLI
- SNOWFLAKE


# PROJECT

1. CREATE SNOWFLAKE CONNECTION WITH AIRFLOW THROUGH UI:
![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/f493aef7-c8a2-4a69-b55e-951fc0d7c4a7)

2. SET UP THE REQUIREMENTS FOLDER WITH SNOWFLAKE airflow provider:
apache-airflow-providers-snowflake==5.1.0
![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/9f62b5f9-2078-4e3b-a965-fbb215a18106)

3. SET UP SODA INTO PYTHON VIRTUAL ENV THROUGH DOCKERFILE:
RUN python -m venv soda_venv && source soda_venv/bin/activate && \
    pip install --no-cache-dir soda-core-snowflake==3.0.47 &&\
    pip install --no-cache-dir soda-core-scientific==3.0.47 && deactivate

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/1ea000a4-417a-4ec2-a244-2fa0fb7aaea6)

4. CREATE ENV VARIABLES:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/401e3958-e8e8-4952-a116-ebbf738da952)


5. CREATE include/soda/configuration.yml:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/e356d978-dd80-47ba-bc1c-87b00385fb68)

6. test the connection: astro dev restart >> source venv/bin/activate >> soda test-connection -d snowflake_db -c include/soda

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/46edce36-478b-4ae9-bcb4-76900c0cfb3b)


7. CREATE CHECK FUNCTION:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/52f503ec-5c0c-4040-8566-4811753f5962)


8. CREATE SODA CHECKS:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/f8d4eae9-4beb-48e7-958b-496a9cc9c28e)

9. INCREMENT THE MAIN dag:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/1a2f814f-c49b-4563-ad84-8028be18503c)


10. run airflow tasks test movie check_movie

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/5719685a-c904-44f5-b6fc-7eb01c614cc5)

11. GET TOP 10 MOVIES WITH TRANSFORM OPERATOR:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/2927759d-21b9-4057-901a-780b4d377eb9)

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/07aea2ba-eba8-4161-98df-f3d4a8973725)


THIS SHOULD RESULT IN THIS STRUCTURE INSIDE AIRFLOW UI:


![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/baecccd0-1b99-47ba-9bd3-8c621c170509)


12. RUN THE MOVIE DAG AND CHECK THE SNOWFLAKE FOR NEW TOP 10 TABLE:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/07b97061-ee0f-44fe-9b75-acc042caee50)


![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/01a2e059-fa89-49c3-986c-5edf2e208dab)



13. NOW LETS CHECK THE TOP 10 TABLE WITH SODA AS WELL:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/fb6352ac-f576-4b28-baa1-5431c7ab6546)


![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/965d1ab3-3f69-427f-9076-21636d465de0)


AND VOILÁ:

![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/c9fe6d77-5df7-4685-b973-fe327e579bbb)


![image](https://github.com/EduAFernandes/Airflow-Soda-Snowflake/assets/78389579/33e02fad-4ac6-49b2-bbe3-7678b2ce1543)






