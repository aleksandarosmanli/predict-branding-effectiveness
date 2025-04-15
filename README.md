# Predict-Branding-Effectiveness
Project for predicting branding effectiveness from employees' and customers' perspectives

This research presents a supervised learning framework that applies machine learning models, including feedforward neural networks (FNNs), to predict branding effectiveness and evaluate its drivers across employee and customer groups. The analysis focuses on two types of brand metrics: perception metrics (brand awareness, familiarity, and care) and behavioral metrics (decision to buy and loyalty). Multiclass classification techniques are used for these two types of brand metrics. The study identifies the most influential predictors associated with positive branding effectiveness by training models on structured organizational and behavioral data. It also evaluates how different metrics (e.g., precision, recall, F1-score, and AUC) capture performance across different ML models. The findings offer actionable insights into branding effectiveness and demonstrate the practical value of machine learning in uncovering perceptual gaps and engagement drivers. The research is positioned at the intersection of applied AI, organizational analytics, and brand strategy.

I.	INTRODUCTION

In today’s competitive and highly digitized markets, a company’s brand represents far more than its logo or tagline. It encapsulates collective perceptions, values, and experiences held by both employees and customers. Measuring and managing brand-related constructs such as awareness, engagement, and effectiveness has become a key strategic priority, particularly in industries where trust, loyalty, and internal alignment are vital. Traditionally, brand assessment relies heavily on qualitative feedback, surveys, or Net Promoter Scores (NPS), offering only partial visibility into the drivers of brand perception. However, with the increasing availability of structured internal and external data, machine learning (ML) and neural network models offer new possibilities for quantifying, modeling, and predicting brand outcomes with greater nuance and scalability.
This research presents an applied machine learning framework designed to capture and predict two types of brand metrics, perception and behavioral metrics, based on insights gathered from the company’s employees and customers. The study incorporates multiclass classification for grading the branding effectiveness from “Not Effective” to “Excellent”. Feedforward neural networks (FNNs), in combination with classical ML algorithms, are trained on these structured organizational metrics and survey data to explore which predictors most significantly influence their perception of branding effectiveness.


II.	BRANDING EFFECTIVENESS

Determining the key impact features on branding effectiveness is crucial for every company because branding is about shaping how people perceive the company, and that perception directly impacts customer behavior, loyalty, and revenue.
For that purpose, I used three questionnaires for company employees, residential and business customers. The participants rated the branding effectivess on a five-point ordinal scale ranging from "Not Effective" to "Excellent”, enabling a more granular classification.
What distinguishes this study is its dual-perspective approach. Both employee and customer datasets were used to explore variations in branding effectiveness evaluation. This allows to detect perceptual misalignments that might otherwise go unnoticed through conventional feedback mechanisms. For instance, a brand that is well-understood by customers but poorly articulated internally may face operational inconsistencies that hinder its effectiveness.
Predictive feature sets were carefully chosen, preprocessed, and encoded to support multiple modeling pipelines, including FNNs and decision trees. For every research topic, the chosen feature set leads the interviewed employee or customer to answer the corresponding “target” question. Based on all the answers to the target question, ML models predict the features’ impact on the target question. 
By applying interpretable models alongside high-performing neural networks, I gain both predictive accuracy and actionable insights. Feature impact, as a key output metric, helps organizations to evaluate branding effectiveness, offering a foundation for strategic improvement.


III.	RESEARCH PROCESS AND DATA COLLECTION

For the purpose of this research, a Macedonian telecommunications operator was chosen, which offers to its customers a wide array of top excellence telecommunication services and contents within the scope of the fixed and mobile networks, broadband services, and integrated solutions, also including TV over Internet Protocol (IPTV). The Company’s product portfolio includes Internet Protocol–based services, data transfer, sale and lease of equipment, and services for system integration. The company currently consists of four different departments.
It uses a deductive research approach by using the same questionnaire structured for the three different types of survey participants:
•	company’s employees,
•	company’s residential customers, and
•	company’s business customers.
The questions consider two types of brand metrics: questions from 1 to 5 - perception metrics, and questions from 6 to 13 – behavioral metrics.
The responses from these questionnaires are used to predict the impact of every metric on the corresponding target questions.
The datasets consisting these results were used as an input to two different tree-based ML models: Random Forest and CatBoost, as well as Feedforward Neural Network (FNN) with different architecture to predict the impact of every “feature” questions representing brand metrics on the “target” feature – evaluation of the branding effectivess. I chose these two tree-based models because they are both powerful, non-linear models that can handle complex relationships between features and the target variable while being robust to overfitting and capable of handling categorical data efficiently. I also chose the FNN because it can capture complex, non-linear relationships between features and the target variable, leveraging its deep learning architecture to model intricate patterns in the data.
In order to determine the impact of each feature on the model‘s target prediction, I chose the SHAP (Shapley Additive exPlanations) method for both ML and FNN models.
Taking into account that the case company consists of four departments, in the first three questionnaires, from every different department 250 employees were interviewed, or in total, 1.000 employees from the whole company. This representative sample was chosen regarding the company’s structure and its total number of employees.
For the purpose of the customer questionnaire, 7.000 residential and 3.000 business customers were interviewed.
The results from the 3 different models are shown in the corresponding tables. Every table consists of four columns: Feature (short description of the feature), Impact % (feature impact on the model‘s target prediction in percentage), Impact Direction (direction of the feature impact on the model’s target prediction – Inc. or Dec.), and Impact Strength (the strength of the feature impact on the model‘s target prediction – High, Medium or Low).

A.	Company’s Employees

The corresponding questionnaire for company’s employees is consisting of 13 questions which measure employee’s opinion on every metric by answering “Yes”, “No” or “Not Sure”, and one “target” question to evaluate the branding effectivess in a Liker-scale from 0 (“Not Effective”) to 4 (“Excellent”) as shown on “Table I”.
“Tables II, III, and V” show the features with the top impact on the model‘s prediction regarding employees’ evaluation of their company’s branding effectiveness for the three ML models: Random Forest, CatBoost, and FNN. “Tables IV and VI” show the corresponding model test scores.
From the “Table II”, it is clear that employees’ belief that customers perceive the brand as premium-priced contributes positively—though to a smaller extent—to branding effectiveness. This suggests that perceived premium value, when recognized internally, can reinforce brand positioning.
Interestingly, stronger employee perceptions of the brand’s distinctiveness are associated with a high negative impact on branding effectiveness. This may point to a potential misalignment between what employees view as brand uniqueness and how effectively it resonates with customers. 
Consistent with earlier results, employee expectations about customers’ intent to buy show a high negative association with branding effectiveness, possibly reflecting over-optimism or a gap between assumed and actual purchase behavior.
From the “Table III”, it is clear that an increase in employees’ evaluation of customers’ willingness to recommend the company’s products and services has a strong positive impact on branding effectiveness. Also, stronger employee perceptions of the company’s product or service quality are associated with a significantly positive effect on branding effectiveness. When employees believe that customers are more spontaneously aware of the brand, it contributes strongly and positively to branding effectiveness.
Higher employee expectations of customer purchase intention appear to be strongly associated with a decrease in perceived branding effectiveness. Also, employees’ stronger belief in the rational superiority of the brand is linked with a high negative impact on branding effectiveness, suggesting potential overconfidence or a disconnect with customer sentiment. A stronger employee belief that the brand is actively communicated or promoted ('brandful') is associated with a notable negative effect on branding effectiveness, potentially indicating oversaturation or misalignment with customer perception.
Both ML models show high values for the test metrics, as shown on “Table IV”.
For the FNN network, I used 17 input neurons (each input neuron for a different feature) and 5 output neurons, one for each different answer on the “target” branding effectiveness evaluation question. To find the best-performing FNN architecture, I tested several architectures with 2 hidden layers with different numbers of neurons.
“Table V” shows that employees from the services and marketing departments show a high positive impact on branding effectiveness. This suggests that individuals in these roles may be more attuned to customer needs and external brand communication, thereby enhancing the company's branding performance through their perceptions and actions.
On the other hand, affiliations with the finance and sales departments are associated with a high negative impact on branding effectiveness. This could indicate a potential misalignment between the objectives or communication styles of these departments and the broader branding strategy. It may also reflect that employees in these areas are less directly engaged with the brand’s emotional or experiential dimensions that resonate with customers.
The best test scores come from FNN (17,34,17,5) as shown on “Table VI”.

B.	Company’s Residential Customers

The corresponding questionnaire for company’s residential customers has the same 13 questions as the questionnaire for the company’s employees, with the only difference in the way how each question is posed to the customers.
“Tables VII, VIII, and X” show the features with the top impact on the model‘s prediction regarding residential customers’ evaluation of the company’s branding effectiveness for the three ML models: Random Forest, CatBoost, and FNN. “Tables IX and XI” show the corresponding model test scores.
“Table VII” shows that residential customers who express a stronger intention to buy the company’s products or cite specific reasons for trying the brand tend to associate this positively with branding effectiveness. These factors indicate that when customers feel personally motivated or curious to engage with the brand, it strengthens their overall perception of the brand’s value and appeal.
On the other hand, when residential customers are less inclined to recommend the company to others or perceive the brand quality as lower, these views are strongly linked with a negative impact on branding effectiveness. This suggests that a lack of advocacy and perceived excellence significantly weakens how effective the brand is seen, potentially affecting customer trust and loyalty.
“Table VIII” shows that among residential customers, a strong intention to purchase the company’s products and a willingness to recommend them to others are both highly impactful and positively associated with branding effectiveness. These two indicators reflect not only satisfaction but also active brand engagement, reinforcing the brand’s resonance and relevance in the eyes of its customers.
On the other hand, perceptions related to brand distinctiveness and brand awareness formed through indirect exposure (i.e., inductively brand aware) are both linked to a high negative impact on branding effectiveness. This may suggest that while customers recognize the brand or find it unique, such recognition alone—especially if not based on direct experience or value perception—does not guarantee a favorable branding outcome. Instead, it highlights the risk of superficial brand visibility that doesn’t translate into trust or preference.
CatBoost outscored the Random Forest model on the test metrics, as shown on “Table IX”.
For the FNN network, I used 13 input neurons (each input neuron for a different feature) and 5 output neurons, one for each different answer on the “target” branding effectiveness evaluation question. To find the best-performing FNN architecture, I tested several architectures with 2 hidden layers with different numbers of neurons.
“Table X” shows that residential customers who express interest in trying the brand, perceive it as competitive, or associate it with a premium offering contribute positively to branding effectiveness, albeit at a lower magnitude compared to more prominent drivers. These findings suggest that even subtle motivations—like curiosity, comparative advantage, or premium perception—play a meaningful role in shaping a brand’s appeal and effectiveness.
Conversely, several indicators demonstrate a high negative impact on branding effectiveness. Notably, customers who view the brand as brandful (overly commercial or exaggerated in its self-presentation) or who are aware of the brand through indirect exposure tend to associate it with lower effectiveness. This suggests that brand visibility without substantive personal value may even backfire.
Furthermore, negative impact is also observed among customers who perceive the brand's quality unfavorably or who are dissatisfied after purchase. These insights underline a critical need to ensure that customer expectations align with actual brand experience, especially after the purchase, where unmet expectations can significantly erode brand trust and effectiveness.
The best test scores come from FNN (13,52,26,5) as shown on “Table XI”.

C.	Company’s Business Customers

The corresponding questionnaire for the company’s business customers has the same 13 questions as the questionnaire for the company’s residential customers.
“Tables XII, XIII, and XV” show the features with the top impact on the model‘s prediction regarding business customers’ evaluation of the company’s branding effectiveness for the three ML models: Random Forest, CatBoost, and FNN. “Tables XIV and XVI” show the corresponding model test scores.
“Table XII” shows that among business customers, positive intentions and perceptions are key drivers of branding effectiveness. Specifically, when businesses recommend the company’s products and services to others or express an intent to purchase, these sentiments strongly contribute to higher branding effectiveness. These findings highlight the importance of fostering trust and satisfaction that leads to advocacy and purchase readiness within the B2B segment.
In addition, business customers who associate the brand with a premium offering also positively influence branding outcomes. This suggests that premium positioning, when aligned with customer expectations, can enhance the perceived value and effectiveness of the brand in a competitive market.
However, a notable exception lies in perceptions of brand quality, which show a high negative association with branding effectiveness. This may indicate a discrepancy between expected and delivered quality among business customers, signaling that quality assurance and consistency are crucial areas for improvement in the B2B experience.
For business customers, brand advocacy, purchase intention, and perceived brand integration emerge as powerful contributors to branding effectiveness. When businesses are willing to recommend the company’s products and services, express strong intent to buy, and feel that the brand is deeply embedded in their operations or identity, branding performance significantly improves. These findings suggest that emotional buy-in and strategic alignment with the brand are vital in the B2B context.
However, two insights point to areas of potential misalignment. Business customers who perceive the brand as highly distinctive show a strong negative association with branding effectiveness. This could indicate that excessive uniqueness or differentiation is not necessarily resonating or meeting the practical needs of business clients, possibly creating confusion or a disconnect.
Similarly, lower branding effectiveness is also associated with higher reported satisfaction after purchase. This somewhat counterintuitive result might reflect post-purchase overcompensation or unmet pre-purchase expectations, where satisfaction is acknowledged but not aligned with deeper brand loyalty or advocacy.
CatBoost outscored the Random Forest model on the test metrics, as shown on “Table XIV”.
For the FNN network, I used the same architecture of the FNN network as for the residential customers.
From “Table XV” it is clear that among business customers, perceptions of brand distinctiveness and the belief that the company’s offerings are premium in nature both show a moderate positive association with branding effectiveness. This suggests that differentiation and perceived value play an important role in shaping brand success within the B2B market.
When business clients recognize a brand as unique within the competitive landscape and view its products or services as premium quality, it moderately enhances their overall impression of the brand. These insights imply that positioning the brand with a clear, high-value proposition resonates well with professional buyers, even if the impact is not as strong as more emotional or advocacy-driven factors.
Interestingly, several key perceptions held by business customers—such as satisfaction after purchase, a sense of brand pride or enthusiasm, intent to buy, and brand quality—all show a strong negative association with branding effectiveness.
This pattern may indicate a disconnect between perceived satisfaction or product quality and the overall brand resonance or identity. While business customers might express positive views in isolation, these sentiments may not necessarily translate into stronger brand effectiveness. It’s possible that functional satisfaction is not enough in the B2B space without deeper alignment with brand values, innovation, or relationship-building.
These findings highlight the importance of not just delivering on quality and satisfaction but also ensuring that the brand’s emotional and strategic positioning connects meaningfully with professional decision-makers.
The best test scores come from FNN (13,52,26,5) as shown on “Table XVI”.


IV.	CONCLUSIONS

In this study, three distinct ML models: Random Forest (RF), CatBoost, and Feedforward Neural Network (FNN) - were employed to analyze the impact of various features on brand perception. By comparing the identified top impact features from each model, I gain insights into the different ways each model approaches the feature importance problem.
The comparative analysis underscores the complementary nature of different ML models in understanding branding effectiveness. While tree-based models highlight the importance of measurable, straightforward features, neural networks open the door to exploring deeper, less obvious aspects of branding effectiveness. Future research could explore hybrid approaches, combining the strengths of both model types, to further refine the understanding of branding effectiveness perception and its drivers.



