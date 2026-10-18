# Rider Delivery Cost Gap Analysis Dashboard

**Power BI | Business Intelligence | Operational Analytics | Cost Optimization**

An interactive Power BI dashboard designed to analyse delivery fee recovery, rider earnings, and delivery cost gaps across zones, rider types, and time periods.

The project demonstrates how operational and financial data can be transformed into actionable insights to investigate delivery subsidies, evaluate cost efficiency, and support data-driven decisions in a food-delivery business.

> **Data Disclaimer:** This is an independent portfolio project built using synthetic/generated data. All figures and patterns are illustrative and do not represent actual Pathao operational or financial performance. This project is not an official Pathao report and is not affiliated with Pathao.

## 1. Business Problem

In a food-delivery business, the amount charged to customers for delivery may differ from the amount paid to riders to complete those deliveries.

When rider earnings consistently exceed delivery fee revenue, the platform must cover the difference through other revenue sources. However, the size of this gap can vary across zones, rider types, and time periods.

Without a structured monitoring system, it can be difficult to identify:

- Where delivery costs exceed delivery fee revenue.
- Which zones contribute most to the overall delivery cost gap.
- Which rider types have relatively high average delivery cost gaps.
- Whether delivery fee recovery is improving or deteriorating over time.
- Which operational segments require further investigation to improve delivery economics.

This project addresses these questions through an interactive dashboard that connects delivery fee revenue, rider earnings, delivery volumes, and cost gap analysis.

## 2. Project Objectives

- Compare delivery fees charged to customers with rider earnings.
- Measure the total delivery cost gap and average gap per recorded delivery.
- Calculate the delivery fee recovery rate.
- Identify orders where rider earnings exceed the delivery fee charged.
- Compare delivery cost exposure across zones and rider types.
- Monitor monthly and daily changes in delivery costs and fee recovery.
- Identify high-impact operational segments for further investigation.
- Support evidence-based evaluation of delivery pricing and rider cost efficiency.

## 3. Key Performance Indicators (KPIs)

### Total Riders

Counts riders who appear in the selected dataset and have recorded delivery activity.

**Business purpose:** Monitor the size of the active delivery population represented in the selected period.

### Total Deliveries

Measures the total number of deliveries represented in the dataset.

**Business purpose:** Understand delivery volume and provide context for cost and efficiency metrics.

### Delivery Charged

The total delivery fee revenue charged to customers, represented by `DeliveryFeePathao`.

**Business purpose:** Measure the delivery fee revenue available to offset rider delivery costs.

### Rider Earnings

The total amount paid or payable to riders for deliveries, represented by `RiderEarning`.

**Business purpose:** Monitor the cost of fulfilling deliveries.

### Total Delivery Cost Gap

**Formula:**

`Total Cost Gap = Total Rider Earnings − Total Delivery Fee Revenue`

**Business purpose:** Quantify the difference between rider delivery costs and delivery fee revenue.

- Positive gap: Rider earnings exceed delivery fee revenue, indicating potential delivery subsidy exposure.
- Zero gap: Delivery fee revenue equals rider earnings.
- Negative gap: Delivery fee revenue exceeds rider earnings before considering other delivery-related costs.

A positive gap does not automatically mean the overall order is unprofitable because commission and other revenue components may contribute to total order economics.

### Average Delivery Cost Gap

**Formula:**

`Average Gap = Average of (Rider Earnings − Delivery Fee Revenue)`

The current dashboard calculates the average difference at the financial dataset's row level.

**Business purpose:** Understand the typical cost gap per recorded row. If each row represents exactly one delivery, this can be interpreted as the average gap per delivery. If orders have multiple rows, the calculation should be adjusted to the appropriate order-level grain.

### Loss Order Percentage

**Formula:**

`Loss Order % = Rows Where Rider Earnings Exceed Delivery Fee ÷ Total Rows`

The current measure represents the percentage of records where rider earnings exceed delivery fee revenue.

**Business purpose:** Estimate how frequently the delivery fee fails to cover rider earnings in the current dataset.

For an order-level KPI, the calculation should instead compare the total rider earnings and delivery fee for each distinct order. This avoids treating multiple records from the same order as separate loss orders.

### Delivery Recovery Rate

**Formula:**

`Delivery Recovery Rate = Total Delivery Fee Revenue ÷ Total Rider Earnings`

**Business purpose:** Measure the proportion of rider earnings covered by delivery fee revenue.

For example, a recovery rate of 0.62 means that delivery fee revenue covers 62% of rider earnings. The remaining 38% represents the uncovered portion of rider earnings before considering other revenue or cost components.

A higher recovery rate indicates stronger delivery fee coverage, but it should be evaluated alongside customer pricing, order demand, and overall gross margin.

## 4. Dashboard Features & Visual Analysis

### A. Rider Performance Overview

**Visual:** Rider performance table

Displays rider identifiers, rider names, and total deliveries.

**Business questions:**
- How is delivery volume distributed across riders?
- Which riders have the highest recorded delivery counts?
- Are delivery volumes concentrated among a small group of riders?

**Business value:** Provides a starting point for operational workload analysis and rider-level investigation.

Delivery count alone should not be treated as a complete performance score. Fair comparisons may also require working hours, assigned orders, delivery distance, and completed versus cancelled deliveries.

### B. Monthly Delivery Cost Trend

**Visual:** Monthly line or area chart comparing rider delivery costs over time.

**Business questions:**
- How do rider earnings change month by month?
- Are delivery costs increasing or decreasing?
- Do cost changes correspond to changes in delivery volume?

**Business value:** Helps management distinguish increases caused by higher demand from increases in average delivery cost.

### C. Monthly Delivery Fee Revenue

**Visual:** Monthly trend of delivery fees charged to customers.

**Business questions:**
- How does delivery fee revenue change over time?
- Is delivery fee revenue keeping pace with rider earnings?
- Are changes in delivery fee revenue associated with changes in delivery volume?

**Business value:** Supports monitoring of delivery fee recovery and the relationship between customer charges and delivery costs.

### D. Delivery Volume by Rider Type

**Visual:** Column chart comparing total deliveries by rider type.

**Business questions:**
- Which rider types handle the largest delivery volumes?
- How is delivery activity distributed across rider categories?
- Which rider types should be examined further for cost efficiency?

**Business value:** Provides context for evaluating the relative scale and economics of different rider categories.

### E. Delivery Cost Gap by Zone

**Visual:** Treemap comparing delivery cost gaps across zones.

**Business questions:**
- Which zones contribute most to the total delivery cost gap?
- Where is the largest absolute difference between rider earnings and customer delivery fees?
- Which zones should be prioritized for further investigation?

**Business value:** Helps prioritize zones based on their contribution to the total financial gap.

Absolute cost gap should be considered alongside delivery volume and gap per order. A large zone may have a large total gap simply because it handles more deliveries.

### F. Delivery Cost Gap by Month and Day

**Visual:** Daily or monthly line chart of delivery cost gap.

**Business questions:**
- When does the cost gap increase or decrease?
- Are there periods with unusually high delivery subsidy exposure?
- Do changes align with delivery volume or average gap per order?

**Business value:** Supports investigation of time-based patterns and helps identify periods that warrant operational review.

### G. Average Delivery Cost Gap by Rider Type

**Visual:** Bar chart comparing average delivery cost gap across rider types.

**Business questions:**
- Which rider types have the highest average gap?
- Which categories recover a greater share of rider earnings through delivery fees?
- Do high-volume rider types also have high average cost gaps?

**Business value:** Helps compare rider categories using unit-level cost indicators rather than total costs alone.

## 5. Potential Operational and Financial Issues to Investigate

The dashboard supports the investigation of several potential issues.

### Delivery Subsidy Exposure

A high positive delivery cost gap indicates that delivery fee revenue does not fully cover rider earnings.

**Potential action:** Review zone-level delivery pricing, delivery distance, minimum basket thresholds, and other revenue contributions before considering pricing changes.

### Zone-Level Cost Concentration

Some zones may contribute a disproportionately large share of the total gap.

**Potential action:** Compare total gap, gap per delivery, recovery rate, and delivery volume to determine whether the result reflects scale or weaker unit economics.

### Rider-Type Cost Differences

Average delivery cost gaps may differ across rider categories.

**Potential action:** Investigate differences in payment structures, delivery distance, workload, and order allocation before making changes to rider compensation or allocation.

### Declining Delivery Fee Recovery

If rider earnings grow faster than delivery fee revenue, the recovery rate may deteriorate.

**Potential action:** Decompose changes in delivery volume, average delivery fee, and average rider earnings to determine the underlying driver.

### Unusual Daily Cost Movements

Sharp changes in daily cost gaps may indicate shifts in delivery mix, demand, pricing, or data quality.

**Potential action:** Investigate the relevant dates and compare the total gap with the gap per order and delivery volume.

These are potential investigation areas, not confirmed operational problems. The dataset is synthetic, and any real-world conclusion would require validated operational and financial records.

## 6. Additional Analysis Opportunities

| Analysis | Business Purpose |
|---|---|
| Delivery Cost Gap per Order | Compare unit-level delivery economics across zones and rider types. |
| Recovery Rate by Zone | Identify areas with weaker delivery fee coverage. |
| Cost Gap vs. Delivery Volume | Separate high total cost caused by scale from high unit-level cost. |
| Delivery Fee and Rider Earnings per Order | Identify which component drives changes in the gap. |
| Monthly Recovery Rate Trend | Monitor whether delivery fee coverage is improving. |
| Rider-Type Cost Efficiency | Compare average cost and fee recovery across rider categories. |
| Outlier Detection | Identify unusually high or low delivery cost gaps for investigation. |
| Gross Margin Integration | Evaluate whether delivery subsidy exposure is offset by commission and other revenue. |

## 7. Technical Skills Demonstrated

### Power BI & Data Visualization
- Interactive dashboard development
- KPI cards and date/zone slicers
- Trend analysis and comparative charts
- Treemap-based zone analysis
- Rider-type and rider-level performance reporting

### DAX & Business Metrics
- Financial aggregations using `SUM`
- Average cost gap calculations using `AVERAGEX`
- Conditional record analysis using `FILTER`
- Ratio calculations using `DIVIDE`
- Delivery fee recovery analysis
- KPI design and interpretation

### Business & Operational Analysis
- Delivery cost and revenue comparison
- Cost gap investigation
- Zone-level financial analysis
- Rider-type performance comparison
- Operational trend monitoring
- Data-driven problem-solving

## 8. Data Quality & Methodology

Reliable cost analysis depends on understanding the dataset's structure and financial definitions.

Important validation steps include:

- Confirming whether each row represents one order, one delivery, or a transaction-level record.
- Checking whether rider earnings and delivery fees are recorded at the same level of detail.
- Avoiding duplicate counting when calculating deliveries, riders, and cost totals.
- Defining the treatment of cancelled, failed, or reassigned deliveries where applicable.
- Verifying the date field used for monthly analysis.
- Distinguishing delivery fee recovery from overall order profitability.

The delivery cost gap measures the difference between two specified components. It does not represent the platform's complete profit or loss from a delivery.

## 9. Project Outcome

This project demonstrates how Power BI can be used to transform delivery operations data into an interactive cost-monitoring and investigation tool.

It connects delivery fee revenue, rider earnings, cost gaps, and operational segmentation to help stakeholders:

- Understand delivery cost coverage.
- Identify zones contributing most to the total gap.
- Compare delivery economics across rider types.
- Monitor changes in cost and recovery over time.
- Prioritise potential delivery subsidy issues for further investigation.
- Explore opportunities to improve delivery economics while considering customer demand and service quality.

The project's central focus is not simply reporting delivery costs, but using structured analysis to understand the drivers behind those costs and support better-informed operational decisions.
