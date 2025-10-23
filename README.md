# SPYDER

https://www.energytariffscheck.com/ 

SPYDER is an AI-driven platform for the energy sector. It was designed to ingest, process, and make sense  of complex energy tariff data to provide actionable insights - a similar challenge to making sense of contract and generation data for policy compliance and reporting.   
 
A Net Zero initiative Price comparison platform. it is  designed to helps you find the best electricity tariff at the most competitive price. Compare different tariffs, check prices and choose the right option to save on energy bills. The Reader also serves as a forecasting system, a settlement tool and a Net Zero initiative - empowering businesses and consumers with actionable insights for reducing carbon emissions and adopting sustainable energy solutions.   

Hosted on EnergyTariffsCheck.com - https://www.energytariffscheck.com/ , **SPYDER** is a digital representation of a physical energy meter reader utilising real-time energy data, AI-driven analytics, and user-friendly tools to compare tariffs, track consumption,  simulate scenarios, predict outcomes, enable forecasting, facilitate predictive maintenance, and recommend cost-effective renewable energy options.  
  
We have integrated dynamic carbon footprint tracking, personalised energy-saving strategies, and compliance frameworks into a scalable Next.js, TypeScript and Python platform - helping users align sustainability goals with practical, measurable actions.

**Mission**

SPYDER’s mission is to bridge the gap between ambition and implementation in the transition to carbon neutrality. By partnering with green energy providers and leveraging smart algorithms and best practices in OOP, Design Thinking, AI and Machine Learning, the platform is  enabling users to cut costs through personalisation, forecasting, predictive analysis and accelerated maintenance workflows while speeding their Net Zero progress.

A dynamic, virtual representation of a physical Energy Meter Reader, SPYDER mirrors the real-world entity by continuously collecting data from sensors, real-time data streams, data lakes, IoT devices, and other sources. The data is then processed and analyzed to create a digital replica that accurately reflects the behavior, status, and condition of its physical counterpart. By leveraging advanced technologies such as artificial intelligence, machine learning, and predictive analytics, digital twins can simulate various scenarios and predict future outcomes. This enables stakeholders to monitor performance, diagnose issues, optimize processes, and make data-driven decisions in real-time.

This project reflects my passion for using technology as a dual force for environmental and economic impact - turning complex energy decisions into clear, actionable steps for a sustainable future. It follows my work on the OFGEM MHHR initiative. The MHHR is a  transformative energy sector initiative modernising the UK’s electricity settlement system to half-hourly intervals, enabling accurate billing, grid flexibility, and smarter energy use. It paves the way for renewable integration and cost savings for consumers. 

**Key LLM Integration Features**:

✅ Ask Jim:  Custom Domain AI Engine, ML, LLM  RAG Pipeline - https://github.com/kukuu/ask-JIM.

✅ Predictive Maintenance: LLM analyses trends to flag anomalies (e.g., meter failures).

✅ Natural Language Queries (Semantic SEARCH): Users ask, "Show worst-performing meters this week" via chat.

✅ Automated Reports: LangChain generates summaries from Supabase data. Including observability and Monitoring Graphs.

✅ Simulation Scenarios: "What if meter load increases by 20%?" → LLM runs digital twin simulations.



**Repository**  

https://github.com/kukuu/digital-twin-v2 (**PRIVATE** - NodeJS)


**The Nut Cracker**: (Python V4)

https://github.com/kukuu/SPYDER/blob/main/the-nut-cracker.md

_Pipeline Architecture_

```


               DATA INGESTION LAYER
+------------------------------------------------------+
|   Input Sources                                      |
| - Synthetic Data                                     |
| - Excel Files with Meter Consumption Data            |
| - Real-time Streaming of Meter Readings              |
| - API Endpoints for External Data Sources(in-scope)  |
+------------------------------------------------------+
|   Tools                                              |
| - Python (Pandas, OpenPyXL for spreadsheets)         |
| - Kafka or RabbitMQ for real-time streaming          |
+------------------------------------------------------+
                    |
            DATA TRANSFORMATION LAYER
                    |                            
+-------------------------------------------------+
|   Data Cleansing                                |
| - Handle missing,duplicate or invalid meter     |
|    readings                                     |
| - Standardize timestamps and formats            |
+-------------------------------------------------+
|   Data Transformation                           |
| - Aggregate daily, weekly, and monthly readings |
| - Create derived metrics (e.g., avg consumption)|
+-------------------------------------------------+
|   Tools                                         |
| - Python (NumPy, Pandas)                        |
| - PySpark for large-scale processing (Hadoop)   |
+-------------------------------------------------+
                  |
            STORAGE LAYER
                  |
+-------------------------------------------------+
|   Database                                      |
| - PostgreSQL or MySQL for structured data       |
| - Separate tables for sources A, B, and C       |
| - Indexed columns for timestamp-based queries   |
+-------------------------------------------------+
|   Data Lake                                     |
| - S3/Blob Storage for raw and transformed data  |
+-------------------------------------------------+
                   |
             ARCHIVAL SYSTEM
                   |
+-------------------------------------------------+
|   Archival Process                              |
| - Move data older than 30 days to archive folder|
| - Compress files to reduce storage size         |
+-------------------------------------------------+
|   Tools                                         |
| - Python (Schedule/Crontab for automation)      |
| - Cloud Storage (AWS S3, GCP Bucket)            |
+-------------------------------------------------+
                   |
         BATCH PROCESSING & NOTIFICATION LAYER
                   |
+-------------------------------------------------+
|   Scheduled Jobs                                |
| - Batch export of data to stakeholders          |
| - Generate and email reports (PDF/CSV)          |
+-------------------------------------------------+
|   Notification System                           |
| - Send reports to email via SMTP/Payment Gateway |
| - Integrate email notifications with SES/SendGrid|
+-------------------------------------------------+
|   Tools                                         |
| - Python (smtplib, pandas for formatting emails)|
| - Celery + RabbitMQ for batch processing        |
+-------------------------------------------------+
                   |
            MONITORING AND LOGGING
                   |
+-------------------------------------------------+
|   Logging                                       |
| - Track ingestion errors, transformation issues |
| - Log storage/archival successes or failures    |
+-------------------------------------------------+
|   Monitoring                                    |
| - Prometheus for pipeline metrics               |
| - Grafana for real-time dashboards and alerts   |
+-------------------------------------------------+

```

**Technology & Practices**

https://github.com/kukuu/SPYDER/blob/main/technology-and-practices.md

**Scaling**

https://github.com/kukuu/SPYDER/blob/main/scaling.md


**Tariff Calculation Tests and DB Pooling**

https://github.com/kukuu/digital-twin-v2/tree/main/tests

**AI Tools & Framework**

https://github.com/kukuu/SPYDER/blob/main/AI-tools-and-framework.md

**Backend Tools & Integration Practices**

https://github.com/kukuu/SPYDER/blob/main/backend-tools-and-integration-practices.md

## Related resources:

- "Ask JIM" - https://github.com/kukuu/ask-JIM/blob/main/README.md
- Conveyor Belt Simulation: https://github.com/kukuu/IIoT-Digital-Twin-Simulation
- SPIDER Navigation System (SNS): https://github.com/kukuu/spider-navigation-system
- FIFA World Cup 2022: https://github.com/kukuu/FIFA-SaaS-NotificationPlatform-Qatar-WorldCup-2022
- Love Joint: https://www.lovejoint.store/ | https://github.com/kukuu/lovejoint (**PRIVATE**) | https://github.com/kukuu/lovejoint-docs
- AZZOTTO Movies: https://www.azzottomovies.com/trailers | https://github.com/kukuu/azzotto-movies (**PRIVATE**)
- Integration & Cloud Migration: https://github.com/kukuu/integration (**PRIVATE**)



