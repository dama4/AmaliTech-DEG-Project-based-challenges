# Project Brief: The "Last Mile" Logistics Auditor
## A. Executive Summary

Out of 99,441 total orders analyzed, 2,971 were excluded (canceled or missing 
delivery data), leaving 96,470 valid delivered orders for performance auditing. 
Of these, 91.89% were delivered on time, while 3.75% were late and 4.37% were 
super late (more than 5 days past the estimated date). State-level analysis 
revealed severe regional disparities, AL (23.93%), MA (19.67%), and PI (15.97%) 
are the worst-performing states, all located in Brazil's remote northeastern region 
far from major distribution centers. The sentiment impact is stark: late orders 
averaged a review score of 2.57/5 across 7,661 orders, compared to 4.29/5 for 
the 88,163 on-time orders, a gap that directly explains the CEO's spike in 
negative reviews. A Promise Accuracy Risk Monitor was built as a Candidate's 
Choice feature, classifying each state by how accurately delivery dates are 
estimated, giving regional managers an actionable intervention priority list.


## B. Project Links

- **Notebook:** [https://colab.research.google.com/drive/1QINn1wfQxvS9loq9sAHLUgR3hxywS_VK?usp=sharing]
- **Dashboard:** [https://public.tableau.com/app/profile/niyomukiza.damars/viz/VeridiLogisticsDeliveryPerformanceAudit/VeridiLogistics-DeliveryPerformanceAudit?publish=yes]
- **Presentation:** [https://docs.google.com/presentation/d/1haKFi3VW8ZRMtA0iwpYwSG29KQLSBOuu/edit?usp=sharing&ouid=108325113101967390925&rtpof=true&sd=true]

## C. Technical Explanation

### Data Cleaning
- Joined Orders, Reviews, and Customers tables on `order_id` and `customer_id`
- Created `Days_Difference` = `order_estimated_delivery_date` - `order_delivered_customer_date`
- Classified orders as: On Time (≥0 days), Late (0–5 days late), Super Late (>5 days late)
- Excluded canceled and unavailable orders from delivery analysis
- Translated Portuguese product category names to English using `product_category_name_translation.csv`

### Candidate's Choice: Promise Accuracy Risk Monitor
I added a per-state **Promise Accuracy Risk Monitor** that classifies each state into 
one of three risk tiers based on average delivery date error:
- **Over-promising risk**: avg_delay_days < 0 (we consistently deliver later than promised)
- **Balanced promise**: avg_delay_days 0–8 days
- **Conservative promise**: avg_delay_days > 8 days

**Business justification:** The CEO's core concern was not just lateness, but 
inaccurate delivery date estimates. This monitor directly quantifies how badly 
each state is being over-promised, giving regional managers a clear action 
priority list beyond just late %.
### 1. Repository & Code Checks

- [✅] **My GitHub Repo is Public.** (Open the link in a Private/Incognito window to verify).
- [✅] **I have uploaded the `.ipynb` notebook file.**
- [✅] **I have ALSO uploaded an HTML or PDF export** of the notebook.
- [✅] **I have NOT uploaded the massive raw dataset.** (Use `.gitignore` or just don't commit the CSV).
- [✅] **My code uses Relative Paths.**

### 2. Deliverable Checks

- [✅] **My Dashboard link is publicly accessible.** (No login required).
- [✅] **My Presentation link is publicly accessible.** (Permissions set to "Anyone with the link can view").
- [✅] **I have updated this `README.md` file** with my Executive Summary and technical notes.

### 3. Completeness

- [✅] I have completed **User Stories 1-4**.
- [✅] I have completed the **"Candidate's Choice"** challenge and explained it in the README.


---
