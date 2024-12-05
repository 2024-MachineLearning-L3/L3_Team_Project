<h1 class="code-line" data-line-start=0 data-line-end=1 ><a id="1_Website_Fingerprinting_on_the_Tor_Network_0"></a>1. Website Fingerprinting on the Tor Network</h1>
<h2 class="code-line" data-line-start=2 data-line-end=3 ><a id=" 11_Overview_2"></a>📍 1.1 Overview</h2>
<p class="has-line-data" data-line-start="4" data-line-end="5">This project focuses on classifying websites visited over the Tor network by analyzing network traffic patterns. The goal is to evaluate the performance of website fingerprinting models in both <strong>Closed-world</strong> and <strong>Open-world</strong> scenarios.</p>
<h2 class="code-line" data-line-start=6 data-line-end=7 ><a id=" 12_Problem_Definition_6"></a>✏️ 1.2 Problem Definition</h2>
<p class="has-line-data" data-line-start="8" data-line-end="9">Website fingerprinting identifies websites a user visits by analyzing encrypted network traffic patterns. Despite encryption, unique traffic patterns arise from web content like embedded resources and request-response behaviors.</p>
<p class="has-line-data" data-line-start="10" data-line-end="11">In the <strong>Tor network</strong>, which ensures anonymity by encrypting and routing traffic through multiple nodes, attackers can analyze traffic at entry points to infer visited websites. Using Tor traffic data with <strong>timestamped packet sizes</strong>, we aim to classify websites by building and evaluating machine learning models.</p>
<p class="has-line-data" data-line-start="12" data-line-end="13">The project focuses on two scenarios:</p>
<ol>
<li class="has-line-data" data-line-start="14" data-line-end="15"><strong>Closed-world:</strong> Users visit only websites in the training set.</li>
<li class="has-line-data" data-line-start="15" data-line-end="17"><strong>Open-world:</strong> Users visit both monitored and unmonitored websites.</li>
</ol>
<p class="has-line-data" data-line-start="17" data-line-end="18">This project explores the full pipeline, including data preprocessing, feature extraction, model training, and evaluation, to analyze classification performance and traffic patterns.</p>
<h2 class="code-line" data-line-start=19 data-line-end=20 ><a id=" 13_Dataset_19"></a>💽 1.3 Dataset</h2>
<p class="has-line-data" data-line-start="21" data-line-end="22">The dataset consists of two files: <code>mon_standard.pkl</code> and <code>unmon_standard10.pkl</code>. The <code>mon_standard.pkl</code> file contains data from monitored websites with 95 classes representing 95 different websites. It includes 19,000 instances, where each website has 10 subpages observed 20 times. The <code>unmon_standard10_3000.pkl</code> file contains 3,000 instances of unmonitored websites.</p>
<p class="has-line-data" data-line-start="23" data-line-end="24">In the closed-world scenario, it is assumed that users visit only monitored websites. The objective in this case is to classify traffic into the 95 monitored website classes. In the open-world scenario, users can visit both monitored and unmonitored websites. This involves two tasks: binary classification and multi-class classification. For binary classification, monitored instances are labeled as <code>1</code> (positive), and unmonitored instances are labeled as <code>-1</code> (negative). For multi-class classification, monitored instances are assigned labels <code>{0, 1, ..., 94}</code>, and unmonitored instances are labeled as <code>-1</code>.</p>
<h2 class="code-line" data-line-start=25 data-line-end=26 ><a id=" 14_Experiment_Environment_25"></a>⚙️ 1.4 Experiment Environment</h2>
<ul>
<li class="has-line-data" data-line-start="27" data-line-end="32"><strong>Resources</strong>
<ul>
<li class="has-line-data" data-line-start="28" data-line-end="29">Total RAM: 8.00 GB</li>
<li class="has-line-data" data-line-start="29" data-line-end="30">Available RAM: 1.41 GB</li>
<li class="has-line-data" data-line-start="30" data-line-end="32">Total CPU Cores: 8 cores</li>
</ul>
</li>
</ul>
<h2 class="code-line" data-line-start=32 data-line-end=33 ><a id=" 15_Guide_to_Run_the_Project_in_Jupyter_Notebook_32"></a>👟 1.5 Guide to Run the Project in Jupyter Notebook</h2>
<p class="has-line-data" data-line-start="34" data-line-end="35">Follow these steps to execute the project in a Jupyter Notebook environment.</p>
<h3 class="code-line" data-line-start=36 data-line-end=37 ><a id="Step_1_Set_Up_the_Environment_36"></a><strong>Step 1: Set Up the Environment</strong></h3>
<ul>
<li class="has-line-data" data-line-start="38" data-line-end="45">
<p class="has-line-data" data-line-start="38" data-line-end="39"><strong>Install Jupyter Notebook</strong> (if not already installed):</p>
<pre><code class="has-line-data" data-line-start="41" data-line-end="44" class="language-bash">pip install notebook

</code></pre>
</li>
<li class="has-line-data" data-line-start="45" data-line-end="53">
<p class="has-line-data" data-line-start="45" data-line-end="46"><strong>Download the Notebook File</strong>:</p>
<p class="has-line-data" data-line-start="47" data-line-end="48">Go to the project GitHub repository and download the file containing <code>BEST</code> in its name</p>
<ul>
<li class="has-line-data" data-line-start="49" data-line-end="50"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-BEST.ipynb">closed-world/closed-multi-BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="50" data-line-end="51"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-BEST.ipynb">open-world/binary/open-binary-BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="51" data-line-end="52"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature26_BEST.ipynb">open-world/multi/open_multi_up_rf_feature26_BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="52" data-line-end="53"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/extra/extra_DF_BEST.ipynb">extra/extra_DF_BSET.ipynb</a></li>
</ul>
</li>
<li class="has-line-data" data-line-start="53" data-line-end="61">
<p class="has-line-data" data-line-start="53" data-line-end="54"><strong>Open the Notebook</strong>:</p>
<p class="has-line-data" data-line-start="55" data-line-end="56">Place the downloaded notebook file in your working directory, then launch Jupyter Notebook:</p>
<pre><code class="has-line-data" data-line-start="58" data-line-end="61" class="language-bash">jupyter notebook

</code></pre>
</li>
</ul>
<h3 class="code-line" data-line-start=63 data-line-end=64 ><a id="Step_2_Download_the_Dataset_63"></a><strong>Step 2: Download the Dataset</strong></h3>
<ul>
<li class="has-line-data" data-line-start="65" data-line-end="69">
<p class="has-line-data" data-line-start="65" data-line-end="66"><strong>Access the Dataset</strong>:</p>
<p class="has-line-data" data-line-start="67" data-line-end="68">Use the shared drive link: <a href="https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum">https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum</a></p>
</li>
<li class="has-line-data" data-line-start="69" data-line-end="73">
<p class="has-line-data" data-line-start="69" data-line-end="70"><strong>Download Files</strong>:</p>
<ul>
<li class="has-line-data" data-line-start="70" data-line-end="71">Download <code>mon_standard.pkl</code> for monitored websites.</li>
<li class="has-line-data" data-line-start="71" data-line-end="73">Download <code>unmon_standard10_3000.pkl</code> for unmonitored websites.</li>
</ul>
</li>
</ul>
<h1 class="code-line" data-line-start=73 data-line-end=74 ><a id="2_Extra_Credit_73"></a>2. Extra Credit</h1>
<h2 class="code-line" data-line-start=75 data-line-end=76 ><a id=" 21_Overview_75"></a>📍 2.1 Overview</h2>
<p class="has-line-data" data-line-start="77" data-line-end="78">This experiment evaluates the performance of website fingerprinting models on <strong>defended traffic</strong> in the Tor network. The defended traffic employs a <strong>multiple-path communication</strong> defense mechanism to reduce the amount of observable traffic for an attacker. The goal is to determine whether the implemented model can outperform the accuracy of <strong>TrafficSilver-Net</strong>, a baseline model for defended traffic scenarios.</p>
<h2 class="code-line" data-line-start=79 data-line-end=80 ><a id=" 22_Problem_Definition_79"></a>✏️ 2.2 Problem Definition</h2>
<p class="has-line-data" data-line-start="81" data-line-end="82">In a traditional Tor network, attackers can infer user activity by monitoring traffic between the Entry Node and the user. A proposed defense method involves using <strong>multiple communication paths</strong> between the Tor user and middle proxies. This approach reduces the amount of traffic an attacker can observe, potentially mitigating the risk of accurate fingerprinting.</p>
<p class="has-line-data" data-line-start="83" data-line-end="84">The provided defended traffic dataset simulates this defense mechanism. The task is to classify website traffic using the defended dataset and compare the model’s performance to <strong>TrafficSilver-Net</strong>.</p>
<h2 class="code-line" data-line-start=85 data-line-end=86 ><a id=" 23_Guide_to_Run_the_Project_85"></a>👟 2.3 Guide to Run the Project</h2>
<h3 class="code-line" data-line-start=87 data-line-end=88 ><a id="Step_1_Download_the_Dataset_87"></a><strong>Step 1: Download the Dataset</strong></h3>
<ul>
<li class="has-line-data" data-line-start="89" data-line-end="93">
<p class="has-line-data" data-line-start="89" data-line-end="90"><strong>Access the Dataset</strong>:</p>
<p class="has-line-data" data-line-start="91" data-line-end="92">Use the shared drive link: <a href="https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum">https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum</a></p>
</li>
<li class="has-line-data" data-line-start="93" data-line-end="97">
<p class="has-line-data" data-line-start="93" data-line-end="94"><strong>Download Files</strong>:</p>
<ul>
<li class="has-line-data" data-line-start="94" data-line-end="95"><code>ts/mon.zip</code></li>
<li class="has-line-data" data-line-start="95" data-line-end="97"><code>ts/unmon.zip</code></li>
</ul>
</li>
</ul>
<h1 class="code-line" data-line-start=97 data-line-end=98 ><a id="3_Contents_97"></a>3. Contents</h1>
<h2 class="code-line" data-line-start=99 data-line-end=100 ><a id=" 31_Closed_World_Multi_Classification_Experiments_99"></a>📫 3.1 Closed World Multi Classification Experiments</h2>
<p class="has-line-data" data-line-start="101" data-line-end="102">This repository contains experimental code and results for <strong>closed-world multi classification scenarios.</strong> The project explores various techniques to improve classification performance, including feature selection, model selection, hyperparameter optimization. Use <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-BEST.ipynb">closed-multi-BEST.ipynb</a> for the final and best-performing model configuration, along with visual insights into data and model performance. The repository is organized into the following files:</p>
<h2 class="code-line" data-line-start=103 data-line-end=104 ><a id="Files_Overview_103"></a>Files Overview</h2>
<h3 class="code-line" data-line-start=105 data-line-end=106 ><a id="1_closedmultifeature_selectionipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainclosedworldclosedmultifeature_selectionipynb_105"></a>1) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-feature_selection.ipynb">closed-multi-feature_selection.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="107" data-line-end="108"><strong>Purpose</strong>: Compares model performance using <strong>4-feature sets</strong>: 8, 24, 32 and 26 features.</li>
<li class="has-line-data" data-line-start="108" data-line-end="111"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="109" data-line-end="110">Includes results for the 8, 24, 32, 26 features model.</li>
<li class="has-line-data" data-line-start="110" data-line-end="111">Experiments with the 24 features set are integrated into the <code>closed-multi-BEST.ipynb</code> file for final performance.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="111" data-line-end="113"><strong>Outcome</strong>: Demonstrates the significance of feature selection in boosting model accuracy and F1-score.</li>
</ul>
<h3 class="code-line" data-line-start=113 data-line-end=114 ><a id="2_closedmultihyperparametertuningETipynbhttpswwwnotionsoclosedworldmultiaffdef15cd9745a9a6d4562e36d7e9dapvs21_113"></a>2) <a href="https://www.notion.so/closed-world-multi-affdef15cd9745a9a6d4562e36d7e9da?pvs=21">closed-multi-hyperparameter-tuning-ET.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="115" data-line-end="116"><strong>Purpose</strong>: Uses <code>GridSearchCV</code> to find the best hyperparameters for the model.</li>
<li class="has-line-data" data-line-start="116" data-line-end="119"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="117" data-line-end="118">Performs hyperparameter tuning experiments.</li>
<li class="has-line-data" data-line-start="118" data-line-end="119">Finalized hyperparameters are implemented in <code>closed-multi-BEST.ipynb</code>.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="119" data-line-end="121"><strong>Outcome</strong>: Identifies optimal hyperparameters for enhanced performance.</li>
</ul>
<h3 class="code-line" data-line-start=121 data-line-end=122 ><a id="3_closedmultihyperparametertuningRFipynbhttpsgithubcom2024MachineLearningL3L3_Team_ProjectblobmainclosedworldclosedmultihyperparametertuningRFipynb_121"></a>3) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-hyperparameter-tuning-RF.ipynb">closed-multi-hyperparameter-tuning-RF.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="123" data-line-end="124"><strong>Purpose</strong>: Uses <code>RandomizedSearchCV</code> to find the best hyperparameters for the model.</li>
<li class="has-line-data" data-line-start="124" data-line-end="126"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="125" data-line-end="126">Performs hyperparameter tuning experiments.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="126" data-line-end="128"><strong>Outcome</strong>: Identifies optimal hyperparameters for enhanced performance.</li>
</ul>
<h3 class="code-line" data-line-start=128 data-line-end=129 ><a id="4_closedmultimodelselectionipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainclosedworldclosedmultimodelselectionipynb_128"></a>4) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-model-selection.ipynb">closed-multi-model-selection.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="130" data-line-end="131"><strong>Purpose</strong>: finds the most optimal model.</li>
<li class="has-line-data" data-line-start="131" data-line-end="135"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="132" data-line-end="133">Based on 24 fixed features, experiments were conducted with <strong>three models</strong>: Extra Tree, Random Forest, and XGBoost under the same conditions.</li>
<li class="has-line-data" data-line-start="133" data-line-end="135">Extra Tree, which performed best, is applied in the <code>closed-multi-BEST.ipynb</code> file.</li>
</ul>
</li>
</ul>
<h3 class="code-line" data-line-start=135 data-line-end=136 ><a id="5_closedmultiBESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_ProjectblobmainclosedworldclosedmultiBESTipynb_135"></a>5) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-BEST.ipynb">closed-multi-BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="137" data-line-end="138"><strong>Purpose</strong>: Consolidates all the best experimental results and final configurations.</li>
<li class="has-line-data" data-line-start="138" data-line-end="148"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="139" data-line-end="140">Combines the 24 features set, optimized hyperparameters and model.</li>
<li class="has-line-data" data-line-start="140" data-line-end="141">Contains the highest-performing model implementation.</li>
<li class="has-line-data" data-line-start="141" data-line-end="148">Includes detailed result visualizations:
<ul>
<li class="has-line-data" data-line-start="142" data-line-end="143"><strong>Macro-average PR Curve</strong> : Shows the overall Precision-Recall (PR) curve averaged across all classes.</li>
<li class="has-line-data" data-line-start="143" data-line-end="144">
<ul>
<li class="has-line-data" data-line-start="143" data-line-end="144">Precision-Recall Curve per class** : Displays individual PR curves and PR AUC scores for each of the 95 classes.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="144" data-line-end="145"><strong>Top 10 Precision-Recall Curve</strong> : Highlights the PR curves of the top 10 performing classes.</li>
<li class="has-line-data" data-line-start="145" data-line-end="146"><strong>Performance at Different Threshold</strong> : Visualizes the model’s precision, recall, and F1 score performance at various classification thresholds to identify the optimal threshold.</li>
<li class="has-line-data" data-line-start="146" data-line-end="148"><strong>ROC Curve :</strong> Presents ROC curves for each of the 95 classes along with the macro-average ROC curve.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h2 class="code-line" data-line-start=148 data-line-end=149 ><a id=" 32_Open_World_Binary_Classification_Experiments_148"></a>📭 3.2 Open World Binary Classification Experiments</h2>
<p class="has-line-data" data-line-start="150" data-line-end="151">This repository contains experimental code and results for open-world binary classification scenarios. The project explores various techniques to improve classification performance, including feature selection, hyperparameter optimization, and upsampling methods. Use <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-BEST.ipynb">open-binary-BEST.ipynb</a> for the final and best-performing model configuration, along with visual insights into data and model performance. The repository is organized into the following files:</p>
<h2 class="code-line" data-line-start=152 data-line-end=153 ><a id="Files_Overview_152"></a>Files Overview</h2>
<h3 class="code-line" data-line-start=154 data-line-end=155 ><a id="1_openbinaryfeature_selectionipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldbinaryopenbinaryfeature_selectionipynb_154"></a>1) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-feature_selection.ipynb">open-binary-feature_selection.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="156" data-line-end="157"><strong>Purpose</strong>: Compares model performance using two feature sets: 8 features versus 24 features.</li>
<li class="has-line-data" data-line-start="157" data-line-end="160"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="158" data-line-end="159">Includes results for the 8-feature model.</li>
<li class="has-line-data" data-line-start="159" data-line-end="160">Experiments with the expanded 24-feature set are integrated into the <code>open-binary-BEST.ipynb</code> file for final performance.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="160" data-line-end="162"><strong>Outcome</strong>: Demonstrates the significance of feature selection in boosting model accuracy and F1-score.</li>
</ul>
<h3 class="code-line" data-line-start=162 data-line-end=163 ><a id="2_openbinaryhyperparameteripynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldbinaryopenbinaryhyperparameteripynb_162"></a>2) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-hyperparameter.ipynb">open-binary-hyperparameter.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="164" data-line-end="165"><strong>Purpose</strong>: Uses <code>RandomizedSearchCV</code> to find the best hyperparameters for the model.</li>
<li class="has-line-data" data-line-start="165" data-line-end="168"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="166" data-line-end="167">Performs hyperparameter tuning experiments.</li>
<li class="has-line-data" data-line-start="167" data-line-end="168">Finalized hyperparameters are implemented in <code>open-binary-BEST.ipynb</code>.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="168" data-line-end="170"><strong>Outcome</strong>: Identifies optimal hyperparameters for enhanced performance.</li>
</ul>
<h3 class="code-line" data-line-start=170 data-line-end=171 ><a id="3_openbinaryupsamplingipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldbinaryopenbinaryupsamplingipynb_170"></a>3. <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-upsampling.ipynb">open-binary-upsampling.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="172" data-line-end="173"><strong>Purpose</strong>: Addresses dataset imbalance using SMOTE upsampling.</li>
<li class="has-line-data" data-line-start="173" data-line-end="177"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="174" data-line-end="175">Balances the monitored and unmonitored datasets.</li>
<li class="has-line-data" data-line-start="175" data-line-end="177">Final improvements, including reduced false positive rates, are reflected in the <code>open-binary-BEST.ipynb</code> file.</li>
</ul>
</li>
</ul>
<h3 class="code-line" data-line-start=177 data-line-end=178 ><a id="4_openbinaryBESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_ProjectblobmainopenworldbinaryopenbinaryBESTipynb_177"></a>4) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-BEST.ipynb">open-binary-BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="179" data-line-end="180"><strong>Purpose</strong>: Consolidates all the best experimental results and final configurations.</li>
<li class="has-line-data" data-line-start="180" data-line-end="189"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="181" data-line-end="182">Combines the expanded 24-feature set, optimized hyperparameters, and balanced dataset.</li>
<li class="has-line-data" data-line-start="182" data-line-end="183">Contains the highest-performing model implementation.</li>
<li class="has-line-data" data-line-start="183" data-line-end="189">Includes detailed result visualizations:
<ul>
<li class="has-line-data" data-line-start="184" data-line-end="185"><strong>Data Distribution Before and After SMOTE</strong>: Shows class balance improvements through upsampling.</li>
<li class="has-line-data" data-line-start="185" data-line-end="186"><strong>Confusion Matrix</strong>: Highlights model performance in correctly classifying monitored and unmonitored data.</li>
<li class="has-line-data" data-line-start="186" data-line-end="187"><strong>Precision-Recall Curve</strong>: Evaluates precision and recall trade-offs across different thresholds.</li>
<li class="has-line-data" data-line-start="187" data-line-end="189"><strong>ROC Curve</strong>: Demonstrates the model’s ability to distinguish between classes with a high AUC score.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h2 class="code-line" data-line-start=189 data-line-end=190 ><a id=" 33_Open_World_Multi_Classification_Experiments_189"></a>📬 3.3 Open World Multi Classification Experiments</h2>
<p class="has-line-data" data-line-start="191" data-line-end="192">This repository contains experimental code and results for open-world binary classification scenarios. The project explores various techniques to improve classification performance, including feature selection, hyperparameter optimization, and upsampling methods. Use <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature26_BEST.ipynb">open_multi_up_rf_feature26_BEST.ipynb</a> for the final and best-performing model configuration, along with visual insights into data and model performance. The repository is organized into the following files:</p>
<h2 class="code-line" data-line-start=193 data-line-end=194 ><a id="Files_Overview_193"></a>Files Overview</h2>
<h3 class="code-line" data-line-start=195 data-line-end=196 ><a id="1_open_multi_down_feature8_30ipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_down_feature8_30ipynb_195"></a>1) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_down_feature8_30.ipynb">open_multi_down_feature8_30.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="197" data-line-end="198"><strong>Purpose</strong>: experiments with down sampled data, 8 features.</li>
<li class="has-line-data" data-line-start="198" data-line-end="199"><strong>Details</strong>: Includes results for the 8-feature model. (3 models(random forest, gradient boosting, svm)</li>
<li class="has-line-data" data-line-start="199" data-line-end="201"><strong>Outcome</strong>: Demonstrates that the result of down sampling with any model is poor.</li>
</ul>
<h3 class="code-line" data-line-start=201 data-line-end=202 ><a id="2_open_multi_down_rf_feature24_48ipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_down_rf_feature24_48ipynb_201"></a>2) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_down_rf_feature24_48.ipynb">open_multi_down_rf_feature24_48.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="203" data-line-end="204"><strong>Purpose</strong>: experiments with down sampled data, 24 features.</li>
<li class="has-line-data" data-line-start="204" data-line-end="205"><strong>Details</strong>: Includes results for the 24-featured random forest model.</li>
<li class="has-line-data" data-line-start="205" data-line-end="207"><strong>Outcome</strong>: Demonstrates that the result of down sampling with any model and any number of features is poor.</li>
</ul>
<h3 class="code-line" data-line-start=207 data-line-end=208 ><a id="3_open_multi_up_feature_24_xgboostipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_up_feature_24_xgboostipynb_207"></a>3) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_feature_24_xgboost.ipynb">open_multi_up_feature_24_xgboost.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="209" data-line-end="210"><strong>Purpose</strong>: Addresses dataset imbalance using SMOTE upsampling.</li>
<li class="has-line-data" data-line-start="210" data-line-end="212"><strong>Details</strong>: Balances the monitored and unmonitored datasets.</li>
</ul>
<h3 class="code-line" data-line-start=212 data-line-end=213 ><a id="4_open_multi_up_rf_feature24_70ipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_up_rf_feature24_70ipynb_212"></a>4) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature24_70.ipynb">open_multi_up_rf_feature24_70.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="214" data-line-end="215"><strong>Purpose</strong>: Addresses dataset imbalance using SMOTE upsampling.</li>
<li class="has-line-data" data-line-start="215" data-line-end="217"><strong>Details</strong>: Balances the monitored and unmonitored datasets.</li>
</ul>
<h3 class="code-line" data-line-start=217 data-line-end=218 ><a id="5_open_multi_up_rf_feature26_BESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_up_rf_feature26_BESTipynb_217"></a>5) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature26_BEST.ipynb">open_multi_up_rf_feature26_BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="219" data-line-end="220"><strong>Purpose</strong>: Consolidates all the best experimental results and final configurations.</li>
<li class="has-line-data" data-line-start="220" data-line-end="228"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="221" data-line-end="222">Combines the expanded 26-feature set, optimized hyperparameters, and balanced dataset.</li>
<li class="has-line-data" data-line-start="222" data-line-end="223">Contains the highest-performing model implementation.</li>
<li class="has-line-data" data-line-start="223" data-line-end="228">Includes detailed result visualizations:
<ul>
<li class="has-line-data" data-line-start="224" data-line-end="225"><strong>Data Distribution Before and After SMOTE</strong>: Shows class balance improvements through upsampling.</li>
<li class="has-line-data" data-line-start="225" data-line-end="226"><strong>Precision-Recall Curve</strong>: Evaluates precision and recall trade-offs across different thresholds.</li>
<li class="has-line-data" data-line-start="226" data-line-end="228"><strong>ROC Curve</strong>: Demonstrates the model’s ability to distinguish between classes with a high AUC score.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h2 class="code-line" data-line-start=228 data-line-end=229 ><a id=" 34_Extra_Credit_228"></a>💌 3.4 Extra Credit</h2>
<h3 class="code-line" data-line-start=230 data-line-end=231 ><a id="extraextra_DF_BESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainextraextra_DF_BESTipynb_230"></a><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/extra/extra_DF_BEST.ipynb">extra/extra_DF_BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="232" data-line-end="236">
<p class="has-line-data" data-line-start="232" data-line-end="233"><strong>Purpose</strong>:</p>
<p class="has-line-data" data-line-start="234" data-line-end="235">Classify monitored website traffic using the Deep Fingerprinting (DF) model.</p>
</li>
<li class="has-line-data" data-line-start="236" data-line-end="240">
<p class="has-line-data" data-line-start="236" data-line-end="237"><strong>Details</strong>:</p>
<p class="has-line-data" data-line-start="238" data-line-end="239">Parse network data, extract features, and train a neural network for multi-class classification.</p>
</li>
<li class="has-line-data" data-line-start="240" data-line-end="243">
<p class="has-line-data" data-line-start="240" data-line-end="241"><strong>Outcome</strong>:</p>
<p class="has-line-data" data-line-start="242" data-line-end="243">Achieved high accuracy in identifying website traffic patterns.</p>
</li>
</ul>
<h1 class="code-line" data-line-start=245 data-line-end=246 ><a id="4_Members_245"></a>4. Members</h1>
<p class="has-line-data" data-line-start="247" data-line-end="248">Daye Jang, Hayeon Doh, Sejin Park, Sojeong Lee, Sunho Kwak</p>
