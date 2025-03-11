# ✅ PROJECT-05

In this project, the goal is to deliver strategic insights to address key business questions for a supermarket undergoing **modernization**. Leveraging data from a newly implemented storage tool, the analysis focuses on transforming raw information into actionable insights to guide **investment decisions**, **resource optimization**, and **customer service enhancement**.

The choice of **SQL** and **Power BI** as core tools ensures a streamlined and efficient analytical process. **SQL**, known for its robustness and scalability in handling large datasets, is utilized to **manipulate**, **organize**, and **structure** data in a logical and reliable manner. Its capabilities in integrating data from multiple tables and resolving inconsistencies establish a strong foundation for analysis. **Power BI** complements this by enabling the visualization and presentation of data insights, ensuring clarity and accessibility for decision-making.

The project is centered around answering critical business questions, including identifying **profitable product lines**, analyzing **customer behavior patterns**, and optimizing **human resources** in operations. This **question-driven approach** ensures data usage is targeted and impactful, generating tangible value for the organization. The integration of **SQL** and **Power BI** creates a reliable, efficient workflow, delivering high-quality insights to support strategic decision-making.

**Keywords**: SQL, PowerBI, PowerQuery, DAX, Google Cloud Platform, Business Analytics, BigQuery, Data Visualization, Data Analysis.

# ✅ PROCESS

In **Phase 1**, **data transformations** and **manipulations** are conducted using **SQL** within the **Google Cloud Platform (GCP)** environment. The process begins by addressing the **date inconsistencies** in the “Fato_Vendas” table, where all dates were incorrectly recorded as 2019 due to a system issue. These dates are updated to **2022**, retaining their original days and months. A new column, **“vlr_margem_bruta”**, is then created, calculated from **“vlr_preco_total”**, which incorporates unit price and tax. To ensure accuracy, null values in the **“vlr_preco_unitario”** column are corrected using the **average price of the last 20 days**, segmented by **gender**, **product line**, and **branch**. Following these corrections, the **gross margin** calculation is completed. The phase concludes with the creation of a table to distribute a **monthly investment** of **R$ 10,000 per branch**, based on the **number of products sold per product line and month**. This table includes details on **relative participation** and the exact **investment allocation**.

**Phase 2** focuses on **visualizations** and **analyses** in **Power BI**, leveraging direct connections to the GCP-treated tables. The initial objective is to identify the **most promising product line** for **investment in 2023**, evaluating factors such as **monthly sales growth**, **consumer gender**, and **overall performance**. Additionally, **peak demand periods** are analyzed by examining **hourly sales patterns**, enabling the optimal allocation of **outsourced employees** during critical hours. Lastly, **customer satisfaction** by branch is assessed to uncover **service pattern variations** and identify characteristics contributing to potential issues.

# ✅ CONCLUSION

**Phase 1**: The datasets **“fato_vendas”**, **“dim_produto”**, and **“dim_margem_bruta_perc”** were uploaded to the **Google Cloud Platform (GCP)**, enabling data processing in **BigQuery**. This high-performance, managed environment facilitated handling large datasets, reduced infrastructure maintenance complexity, and prepared for future integrations, such as direct **Power BI** connections. Tasks such as **data cleaning**, **standardization**, and **key metric calculations** established a reliable foundation for advanced analytics. BigQuery's distributed architecture ensured fast query execution, while centralizing workflows in GCP eliminated manual pipelines, accelerating **dashboard development** and updates for enhanced productivity.

**Phase 1A**: **Common Table Expressions (CTEs)** were used to modularize database adjustments, improving organization and readability. The focus was on correcting sales dates, updating unit prices, and creating a new **gross margin** column. In **STEP A**, incorrectly recorded dates in **2019** were updated to **2022** using the CTE **“base_data”**, which applied **DATE_ADD** to shift the year forward by three.

**Phase 1B**: In **STEP B1**, null values in **“vlr_preco_unitario”** were corrected by calculating the **average price** from the past 20 days, segmented by **gender**, **product line**, and **branch**, using the CTE **“average_prices.”** These results were applied in the CTE **“corrected_prices”**, filling most missing values, with exceptions where insufficient historical data was available. In **STEP B2**, the **“vlr_margem_bruta”** column was created by combining **tax values** from **dim_produtos** with **gross margin percentages** from **dim_margem_bruta_perc.** This completed the adjustments to dates, prices, and margin calculations.

**Phase 1C**: A monthly investment of **R$10,000 per branch** was distributed based on the number of products sold by **product line** and **month.** The CTE **“vendas_resumidas”** calculated product quantities sold per branch, while **“produtos_totais”** determined total sales per branch and month, enabling relative participation calculations in **“participacao_produtos.”** The CTE **“investimentos_calculados”** proportionally distributed investments, and **“final_table”** joined with **dim_produtos** to display product names alongside their allocated investments.

**Phase 2**: A **Power BI dashboard** was developed to visualize results from BigQuery. With most transformations handled in **GCP**, Power Query overhead was reduced, streamlining model adjustments and enabling near-real-time updates. The dashboard featured dedicated tabs for each business question, allowing users to explore **segmented metrics** and visuals.

**Phase 2A**: A **DAX measure**, **“m_faturamento”**, calculated revenue by multiplying quantities sold by unit prices using **SUMX.** A parameter allowed users to select the primary metric (**Revenue**, **Unit Price**, or **Product Quantity**) for each visualization. Analysis revealed significant growth for **PRODUCT 6** among female customers, rising from **R$57,000 in January** to **R$152,000 in March**, and for **PRODUCT 3** among male customers, increasing from **R$42,000** to **R$151,000** in the same period. These insights highlighted the strategic importance of these products for maximizing financial returns across gender segments.

![Screen-Recording-2025-03-11-at-15 04 00](https://github.com/user-attachments/assets/5a60f2f2-fa7a-4904-bfba-ccbdc80be7e9)

**Phase 2B**: A calculated column, **“periodo_venda”**, was created to group sales into **one-hour intervals.** Using the same **parameter logic** as in previous analyses, the primary metric can be filtered dynamically. Revenue analysis identified the **7:00 PM to 8:00 PM** time slot as the most profitable, generating **R$342,170** across all branches. This period represents the **peak hour** for **Branch B** and is also one of the highest-performing periods for **Branch A.** For **Branch A**, the **12:00 PM to 1:00 PM** interval stands out as a key revenue driver, while **Branch C** experiences its highest profitability between **10:00 AM and 11:00 AM.** These insights inform the optimal allocation of **outsourced staff** to address high-demand periods, prioritizing **7:00 PM to 8:00 PM** for most branches, while also emphasizing **12:00 PM to 1:00 PM** and **10:00 AM to 11:00 AM** for specific locations.

![Screen-Recording-2025-03-11-at-15 04 29](https://github.com/user-attachments/assets/f8d652fe-a0b5-4df6-b484-d18333618d00)

**Phase 2C**: This analysis evaluated variables such as **“num_avaliacao,”** **“nom_filial,”** and related characteristics to detect potential satisfaction issues. The findings reveal that all branches exhibit relatively **similar score distributions**, with **Branch C** standing out for having the **highest number of 10-rated evaluations** and the **lowest incidence of 2-rated scores.** While some differences were observed, such as the predominance of **"member"** or **"normal"** clients and variations in the **most evaluated products**, no significant dissatisfaction trends were identified. **Branch C** demonstrates **stronger engagement** and **positive evaluation outcomes**, suggesting an opportunity to share its **best practices** with other branches rather than addressing isolated shortcomings.

![Screen-Recording-2025-03-11-at-15 04 50](https://github.com/user-attachments/assets/882406ab-2b18-43be-8c2e-dadfbb3be59a)

**Dashboard**: https://app.powerbi.com/reportEmbed?reportId=19b77a80-9c0f-4d1e-abbb-c31f36de517a&autoAuth=true&ctid=d69a7783-e937-4232-ba85-2098408382c8

