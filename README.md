# Palantir-Project
We have build an end-to-end setup in Palantir Foundry to predict project delays and identify potential risks early, using both project schedule data and equipment information.

Predictive Project Delay & Risk Intelligence System

End-to-End ML Application built on Palantir Foundry

📌 Overview

This project is an end-to-end predictive risk intelligence system designed to proactively identify project delays and equipment-related risks using machine learning. Built entirely on Palantir Foundry, the solution integrates project schedules, task progress, cost data, and equipment usage to deliver early warnings, actionable insights, and real-time visibility to project stakeholders.

The system helps answer key operational questions such as:

    1.Which tasks are likely to get delayed and by how many days?

    2.Which equipment types have a higher probability of failure?

    3.Which contractor contributes the most to overall project delays?

    4.Where should teams intervene early to prevent cascading delays?

🎯 Objectives

    1.Predict task-level delays before they occur

    2.Identify equipment failure risks that can impact schedules

    3.Aggregate risks to calculate overall project delay

    4.Provide real-time alerts and an interactive application for monitoring tasks, equipment, and risks

🏗️End-to-End Architecture
1. Data Ingestion & Consolidation

Multiple datasets are ingested and merged into a unified view:

    1.Project metadata (project ID, contractor, location)

    2.Task schedules (start/end dates, progress, dependencies)

    3. Cost and execution data

    4.Equipment usage and historical failure data

All datasets are standardized and merged using Foundry pipelines.

2. Golden Dataset Creation (ML-Ready)

A Golden Project Master Schedule dataset is created through transformations that:

    1.Clean and normalize raw inputs

    2.Engineer features such as:

    3.Task duration and slippage

    4.Contractor workload

Equipment usage frequency

Historical failure indicators

Combine project-level, task-level, and equipment-level attributes

This Golden dataset acts as a single source of truth for:

    1.Model training

    2.Batch predictions

    3.Downstream analytics and applications

3. Machine Learning Models

Two ML models are implemented and integrated directly into Foundry pipelines:

🔹 Random Forest Regressor

    1.Predicts task-level delay (in days)

    2.Uses task progress, dependencies, contractor performance, and equipment risk signals

🔹 Random Forest Classifier

    1.Predicts equipment failure probability

    2.Uses historical failure patterns, usage frequency, and maintenance indicators

Both models:

    1.Are versioned in Foundry’s code repository

    2.Support continuous prediction updates as new data arrives

4. Risk Aggregation Logic

    1.Task delays are aggregated at the contractor level

    2.The contractor with the maximum cumulative delay determines the overall project delay

    3.Equipment failure probabilities are factored into task-level risk scoring

🚨 Alerts & Monitoring

An automated alerting framework is implemented:

🚩 Task Delay Alert

    1.Triggered when predicted delay exceeds 30 days

    2.Identifies specific high-risk tasks

🚧 Equipment Risk Alerts

    1.Highlights equipment with high failure probability

Planned Enhancements

    1.Dependency-aware alerts (impact on downstream tasks)

    2.Project-level risk escalation alerts

🖥️ Interactive Application (Foundry App)

An interactive application was built to provide a single operational control panel for users.

🔹 1. Tasks Information
  
    1.Displays all project tasks with contractor performance

    2.Filterable views for easy navigation

    3.Task-level actions:

        1.View detailed information

        2.Change task priority

        3.Add notes (auto-synced to Notes tab)
        <img width="1864" height="909" alt="unnamed" src="https://github.com/user-attachments/assets/36d823e0-f97d-4a6e-b7d3-6612593e8020" />

<img width="1885" height="915" alt="unnamed" src="https://github.com/user-attachments/assets/f7f319c7-57cd-4269-a920-d6dcdb200d59" />


🔹 2. Equipment Information

    1.Shows equipment usage across projects

    2.Highlights:

        1.Most-used and least-used equipment

        2.Average failure probability per equipment type (from ML model)
<img width="1855" height="917" alt="unnamed" src="https://github.com/user-attachments/assets/264cc7d2-a9ba-435b-8c2b-614f430283a7" />
<img width="1855" height="917" alt="unnamed" src="https://github.com/user-attachments/assets/93768ebb-ff63-426c-aadf-36cdbf559b88" />

🔹 3. Notes

    1.Centralized repository of all user-added notes

    2.Supports operational, execution, and safety instructions

    3.Automatically updated from task interactions
<img width="800" height="162" alt="unnamed" src="https://github.com/user-attachments/assets/6ddd57ee-51f4-4943-8cb3-28ace80c5df6" />

🔹 4. Alerts

    1.Displays ML-driven risk outputs:

        1.Tasks with high delay risk

        2.Equipment with high failure probability

    2.Enables real-time monitoring of critical risks
<img width="1418" height="916" alt="unnamed" src="https://github.com/user-attachments/assets/545351bc-0487-406b-9563-e8a0fbe27952" />

📊 Key Outcomes

    1.Proactive identification of delays before execution impact

    2.Improved coordination between project and equipment teams

    3.Centralized visibility across tasks, equipment, notes, and alerts

    4.Scalable foundation for advanced risk intelligence

🛠️ Tech Stack

    1.Platform: Palantir Foundry

    2.Data Engineering: Foundry Pipelines & Transformations

    3.Machine Learning: Random Forest (Regressor & Classifier)

    4.Application Layer: Foundry Application Framework

    5.Alerts & Monitoring: Automated pipeline-driven alerts

👤 Author

Sumeet Ghodke
Data Analyst | Analytics & ML Engineering
    
