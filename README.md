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





