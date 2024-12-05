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
<li class="has-line-data" data-line-start="38" data-line-end="44">
<p class="has-line-data" data-line-start="38" data-line-end="39"><strong>Install Jupyter Notebook</strong>:</p>
<pre><code class="has-line-data" data-line-start="41" data-line-end="43" class="language-bash">pip install notebook
</code></pre>
</li>
<li class="has-line-data" data-line-start="44" data-line-end="52">
<p class="has-line-data" data-line-start="44" data-line-end="45"><strong>Download the Notebook File</strong>:</p>
<p class="has-line-data" data-line-start="46" data-line-end="47">Go to the project GitHub repository and download the file containing <code>BEST</code> in its name</p>
<ul>
<li class="has-line-data" data-line-start="48" data-line-end="49"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-BEST.ipynb">closed-world/closed-multi-BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="49" data-line-end="50"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-BEST.ipynb">open-world/binary/open-binary-BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="50" data-line-end="51"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature26_BEST.ipynb">open-world/multi/open_multi_up_rf_feature26_BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="51" data-line-end="52"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/extra/extra_DF_BEST.ipynb">extra/extra_DF_BSET.ipynb</a></li>
</ul>
</li>
<li class="has-line-data" data-line-start="52" data-line-end="59">
<p class="has-line-data" data-line-start="52" data-line-end="53"><strong>Open the Notebook</strong>:</p>
<p class="has-line-data" data-line-start="54" data-line-end="55">Place the downloaded notebook file in your working directory, then launch Jupyter Notebook:</p>
<pre><code class="has-line-data" data-line-start="57" data-line-end="59" class="language-bash">jupyter notebook
</code></pre>
</li>
</ul>
<h3 class="code-line" data-line-start=61 data-line-end=62 ><a id="Step_2_Download_the_Dataset_61"></a><strong>Step 2: Download the Dataset</strong></h3>
<ul>
<li class="has-line-data" data-line-start="63" data-line-end="67">
<p class="has-line-data" data-line-start="63" data-line-end="64"><strong>Access the Dataset</strong>:</p>
<p class="has-line-data" data-line-start="65" data-line-end="66">Use the shared drive link: <a href="https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum">https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum</a></p>
</li>
<li class="has-line-data" data-line-start="67" data-line-end="71">
<p class="has-line-data" data-line-start="67" data-line-end="68"><strong>Download Files</strong>:</p>
<ul>
<li class="has-line-data" data-line-start="68" data-line-end="69">Download <code>mon_standard.pkl</code> for monitored websites.</li>
<li class="has-line-data" data-line-start="69" data-line-end="71">Download <code>unmon_standard10_3000.pkl</code> for unmonitored websites.</li>
</ul>
</li>
</ul>
<h3 class="code-line" data-line-start=71 data-line-end=72 ><a id="Step_3_Install_libraries_71"></a>Step 3: Install libraries</h3>
<ul>
<li class="has-line-data" data-line-start="73" data-line-end="75">Python libraries</li>
</ul>
<pre><code class="has-line-data" data-line-start="76" data-line-end="78" class="language-bash">pip install numpy scikit-learn matplotlib tensorflow
</code></pre>
<h1 class="code-line" data-line-start=79 data-line-end=80 ><a id="2_Extra_Credit_79"></a>2. Extra Credit</h1>
<h2 class="code-line" data-line-start=81 data-line-end=82 ><a id=" 21_Overview_81"></a>📍 2.1 Overview</h2>
<p class="has-line-data" data-line-start="83" data-line-end="84">This experiment evaluates the performance of website fingerprinting models on <strong>defended traffic</strong> in the Tor network. The defended traffic employs a <strong>multiple-path communication</strong> defense mechanism to reduce the amount of observable traffic for an attacker. The goal is to determine whether the implemented model can outperform the accuracy of <strong>TrafficSilver-Net</strong>, a baseline model for defended traffic scenarios.</p>
<h2 class="code-line" data-line-start=85 data-line-end=86 ><a id=" 22_Problem_Definition_85"></a>✏️ 2.2 Problem Definition</h2>
<p class="has-line-data" data-line-start="87" data-line-end="88">In a traditional Tor network, attackers can infer user activity by monitoring traffic between the Entry Node and the user. A proposed defense method involves using <strong>multiple communication paths</strong> between the Tor user and middle proxies. This approach reduces the amount of traffic an attacker can observe, potentially mitigating the risk of accurate fingerprinting.</p>
<p class="has-line-data" data-line-start="89" data-line-end="90">The provided defended traffic dataset simulates this defense mechanism. The task is to classify website traffic using the defended dataset and compare the model’s performance to <strong>TrafficSilver-Net</strong>.</p>
<h2 class="code-line" data-line-start=91 data-line-end=92 ><a id=" 23_Guide_to_Run_the_Project_in_Jupyter_Notebook_91"></a>👟 2.3 Guide to Run the Project in Jupyter Notebook</h2>
<h3 class="code-line" data-line-start=93 data-line-end=94 ><a id="Step_1_Set_Up_the_Environment_93"></a><strong>Step 1: Set Up the Environment</strong></h3>
<ul>
<li class="has-line-data" data-line-start="95" data-line-end="101">
<p class="has-line-data" data-line-start="95" data-line-end="96"><strong>Install Jupyter Notebook</strong>:</p>
<pre><code class="has-line-data" data-line-start="98" data-line-end="100" class="language-bash">pip install notebook
</code></pre>
</li>
<li class="has-line-data" data-line-start="101" data-line-end="109">
<p class="has-line-data" data-line-start="101" data-line-end="102"><strong>Download the Notebook File</strong>:</p>
<p class="has-line-data" data-line-start="103" data-line-end="104">Go to the project GitHub repository and download the file containing <code>BEST</code> in its name</p>
<ul>
<li class="has-line-data" data-line-start="105" data-line-end="106"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-BEST.ipynb">closed-world/closed-multi-BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="106" data-line-end="107"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-BEST.ipynb">open-world/binary/open-binary-BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="107" data-line-end="108"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature26_BEST.ipynb">open-world/multi/open_multi_up_rf_feature26_BEST.ipynb</a></li>
<li class="has-line-data" data-line-start="108" data-line-end="109"><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/extra/extra_DF_BEST.ipynb">extra/extra_DF_BSET.ipynb</a></li>
</ul>
</li>
<li class="has-line-data" data-line-start="109" data-line-end="116">
<p class="has-line-data" data-line-start="109" data-line-end="110"><strong>Open the Notebook</strong>:</p>
<p class="has-line-data" data-line-start="111" data-line-end="112">Place the downloaded notebook file in your working directory, then launch Jupyter Notebook:</p>
<pre><code class="has-line-data" data-line-start="114" data-line-end="116" class="language-bash">jupyter notebook
</code></pre>
</li>
</ul>
<h3 class="code-line" data-line-start=118 data-line-end=119 ><a id="Step_2_Download_the_Dataset_118"></a><strong>Step 2: Download the Dataset</strong></h3>
<ul>
<li class="has-line-data" data-line-start="120" data-line-end="124">
<p class="has-line-data" data-line-start="120" data-line-end="121"><strong>Access the Dataset</strong>:</p>
<p class="has-line-data" data-line-start="122" data-line-end="123">Use the shared drive link: <a href="https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum">https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum</a></p>
</li>
<li class="has-line-data" data-line-start="124" data-line-end="128">
<p class="has-line-data" data-line-start="124" data-line-end="125"><strong>Download Files</strong>:</p>
<ul>
<li class="has-line-data" data-line-start="125" data-line-end="126"><code>ts/mon.zip</code></li>
<li class="has-line-data" data-line-start="126" data-line-end="128"><code>ts/unmon.zip</code></li>
</ul>
</li>
</ul>
<h3 class="code-line" data-line-start=128 data-line-end=129 ><a id="Step_3_Install_libraries_128"></a>Step 3: Install libraries</h3>
<ul>
<li class="has-line-data" data-line-start="130" data-line-end="132">Python libraries</li>
</ul>
<pre><code class="has-line-data" data-line-start="133" data-line-end="135" class="language-bash">pip install numpy scikit-learn matplotlib tensorflow
</code></pre>
<h1 class="code-line" data-line-start=136 data-line-end=137 ><a id="3_Contents_136"></a>3. Contents</h1>
<h2 class="code-line" data-line-start=138 data-line-end=139 ><a id=" 31_Closed_World_Multi_Classification_Experiments_138"></a>📫 3.1 Closed World Multi Classification Experiments</h2>
<p class="has-line-data" data-line-start="140" data-line-end="141">This repository contains experimental code and results for <strong>closed-world multi classification scenarios.</strong> The project explores various techniques to improve classification performance, including feature selection, model selection, hyperparameter optimization. Use <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-BEST.ipynb">closed-multi-BEST.ipynb</a> for the final and best-performing model configuration, along with visual insights into data and model performance. The repository is organized into the following files:</p>
<h2 class="code-line" data-line-start=142 data-line-end=143 ><a id="Files_Overview_142"></a>Files Overview</h2>
<h3 class="code-line" data-line-start=144 data-line-end=145 ><a id="1_closedmultifeature_selectionipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainclosedworldclosedmultifeature_selectionipynb_144"></a>1) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-feature_selection.ipynb">closed-multi-feature_selection.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="146" data-line-end="147"><strong>Purpose</strong>: Compares model performance using <strong>4-feature sets</strong>: 8, 24, 32 and 26 features.</li>
<li class="has-line-data" data-line-start="147" data-line-end="150"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="148" data-line-end="149">Includes results for the 8, 24, 32, 26 features model.</li>
<li class="has-line-data" data-line-start="149" data-line-end="150">Experiments with the 24 features set are integrated into the <code>closed-multi-BEST.ipynb</code> file for final performance.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="150" data-line-end="152"><strong>Outcome</strong>: Demonstrates the significance of feature selection in boosting model accuracy and F1-score.</li>
</ul>
<h3 class="code-line" data-line-start=152 data-line-end=153 ><a id="2_closedmultihyperparametertuningETipynbhttpswwwnotionsoclosedworldmultiaffdef15cd9745a9a6d4562e36d7e9dapvs21_152"></a>2) <a href="https://www.notion.so/closed-world-multi-affdef15cd9745a9a6d4562e36d7e9da?pvs=21">closed-multi-hyperparameter-tuning-ET.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="154" data-line-end="155"><strong>Purpose</strong>: Uses <code>GridSearchCV</code> to find the best hyperparameters for the model.</li>
<li class="has-line-data" data-line-start="155" data-line-end="158"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="156" data-line-end="157">Performs hyperparameter tuning experiments.</li>
<li class="has-line-data" data-line-start="157" data-line-end="158">Finalized hyperparameters are implemented in <code>closed-multi-BEST.ipynb</code>.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="158" data-line-end="160"><strong>Outcome</strong>: Identifies optimal hyperparameters for enhanced performance.</li>
</ul>
<h3 class="code-line" data-line-start=160 data-line-end=161 ><a id="3_closedmultihyperparametertuningRFipynbhttpsgithubcom2024MachineLearningL3L3_Team_ProjectblobmainclosedworldclosedmultihyperparametertuningRFipynb_160"></a>3) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-hyperparameter-tuning-RF.ipynb">closed-multi-hyperparameter-tuning-RF.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="162" data-line-end="163"><strong>Purpose</strong>: Uses <code>RandomizedSearchCV</code> to find the best hyperparameters for the model.</li>
<li class="has-line-data" data-line-start="163" data-line-end="165"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="164" data-line-end="165">Performs hyperparameter tuning experiments.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="165" data-line-end="167"><strong>Outcome</strong>: Identifies optimal hyperparameters for enhanced performance.</li>
</ul>
<h3 class="code-line" data-line-start=167 data-line-end=168 ><a id="4_closedmultimodelselectionipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainclosedworldclosedmultimodelselectionipynb_167"></a>4) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-model-selection.ipynb">closed-multi-model-selection.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="169" data-line-end="170"><strong>Purpose</strong>: finds the most optimal model.</li>
<li class="has-line-data" data-line-start="170" data-line-end="174"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="171" data-line-end="172">Based on 24 fixed features, experiments were conducted with <strong>three models</strong>: Extra Tree, Random Forest, and XGBoost under the same conditions.</li>
<li class="has-line-data" data-line-start="172" data-line-end="174">Extra Tree, which performed best, is applied in the <code>closed-multi-BEST.ipynb</code> file.</li>
</ul>
</li>
</ul>
<h3 class="code-line" data-line-start=174 data-line-end=175 ><a id="5_closedmultiBESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_ProjectblobmainclosedworldclosedmultiBESTipynb_174"></a>5) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/closed-world/closed-multi-BEST.ipynb">closed-multi-BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="176" data-line-end="177"><strong>Purpose</strong>: Consolidates all the best experimental results and final configurations.</li>
<li class="has-line-data" data-line-start="177" data-line-end="187"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="178" data-line-end="179">Combines the 24 features set, optimized hyperparameters and model.</li>
<li class="has-line-data" data-line-start="179" data-line-end="180">Contains the highest-performing model implementation.</li>
<li class="has-line-data" data-line-start="180" data-line-end="187">Includes detailed result visualizations:
<ul>
<li class="has-line-data" data-line-start="181" data-line-end="182"><strong>Macro-average PR Curve</strong> : Shows the overall Precision-Recall (PR) curve averaged across all classes.</li>
<li class="has-line-data" data-line-start="182" data-line-end="183">
<ul>
<li class="has-line-data" data-line-start="182" data-line-end="183">Precision-Recall Curve per class** : Displays individual PR curves and PR AUC scores for each of the 95 classes.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="183" data-line-end="184"><strong>Top 10 Precision-Recall Curve</strong> : Highlights the PR curves of the top 10 performing classes.</li>
<li class="has-line-data" data-line-start="184" data-line-end="185"><strong>Performance at Different Threshold</strong> : Visualizes the model’s precision, recall, and F1 score performance at various classification thresholds to identify the optimal threshold.</li>
<li class="has-line-data" data-line-start="185" data-line-end="187"><strong>ROC Curve :</strong> Presents ROC curves for each of the 95 classes along with the macro-average ROC curve.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h2 class="code-line" data-line-start=187 data-line-end=188 ><a id=" 32_Open_World_Binary_Classification_Experiments_187"></a>📭 3.2 Open World Binary Classification Experiments</h2>
<p class="has-line-data" data-line-start="189" data-line-end="190">This repository contains experimental code and results for open-world binary classification scenarios. The project explores various techniques to improve classification performance, including feature selection, hyperparameter optimization, and upsampling methods. Use <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-BEST.ipynb">open-binary-BEST.ipynb</a> for the final and best-performing model configuration, along with visual insights into data and model performance. The repository is organized into the following files:</p>
<h2 class="code-line" data-line-start=191 data-line-end=192 ><a id="Files_Overview_191"></a>Files Overview</h2>
<h3 class="code-line" data-line-start=193 data-line-end=194 ><a id="1_openbinaryfeature_selectionipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldbinaryopenbinaryfeature_selectionipynb_193"></a>1) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-feature_selection.ipynb">open-binary-feature_selection.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="195" data-line-end="196"><strong>Purpose</strong>: Compares model performance using two feature sets: 8 features versus 24 features.</li>
<li class="has-line-data" data-line-start="196" data-line-end="199"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="197" data-line-end="198">Includes results for the 8-feature model.</li>
<li class="has-line-data" data-line-start="198" data-line-end="199">Experiments with the expanded 24-feature set are integrated into the <code>open-binary-BEST.ipynb</code> file for final performance.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="199" data-line-end="201"><strong>Outcome</strong>: Demonstrates the significance of feature selection in boosting model accuracy and F1-score.</li>
</ul>
<h3 class="code-line" data-line-start=201 data-line-end=202 ><a id="2_openbinaryhyperparameteripynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldbinaryopenbinaryhyperparameteripynb_201"></a>2) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-hyperparameter.ipynb">open-binary-hyperparameter.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="203" data-line-end="204"><strong>Purpose</strong>: Uses <code>RandomizedSearchCV</code> to find the best hyperparameters for the model.</li>
<li class="has-line-data" data-line-start="204" data-line-end="207"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="205" data-line-end="206">Performs hyperparameter tuning experiments.</li>
<li class="has-line-data" data-line-start="206" data-line-end="207">Finalized hyperparameters are implemented in <code>open-binary-BEST.ipynb</code>.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="207" data-line-end="209"><strong>Outcome</strong>: Identifies optimal hyperparameters for enhanced performance.</li>
</ul>
<h3 class="code-line" data-line-start=209 data-line-end=210 ><a id="3_openbinaryupsamplingipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldbinaryopenbinaryupsamplingipynb_209"></a>3. <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-upsampling.ipynb">open-binary-upsampling.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="211" data-line-end="212"><strong>Purpose</strong>: Addresses dataset imbalance using SMOTE upsampling.</li>
<li class="has-line-data" data-line-start="212" data-line-end="216"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="213" data-line-end="214">Balances the monitored and unmonitored datasets.</li>
<li class="has-line-data" data-line-start="214" data-line-end="216">Final improvements, including reduced false positive rates, are reflected in the <code>open-binary-BEST.ipynb</code> file.</li>
</ul>
</li>
</ul>
<h3 class="code-line" data-line-start=216 data-line-end=217 ><a id="4_openbinaryBESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_ProjectblobmainopenworldbinaryopenbinaryBESTipynb_216"></a>4) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/binary/open-binary-BEST.ipynb">open-binary-BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="218" data-line-end="219"><strong>Purpose</strong>: Consolidates all the best experimental results and final configurations.</li>
<li class="has-line-data" data-line-start="219" data-line-end="228"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="220" data-line-end="221">Combines the expanded 24-feature set, optimized hyperparameters, and balanced dataset.</li>
<li class="has-line-data" data-line-start="221" data-line-end="222">Contains the highest-performing model implementation.</li>
<li class="has-line-data" data-line-start="222" data-line-end="228">Includes detailed result visualizations:
<ul>
<li class="has-line-data" data-line-start="223" data-line-end="224"><strong>Data Distribution Before and After SMOTE</strong>: Shows class balance improvements through upsampling.</li>
<li class="has-line-data" data-line-start="224" data-line-end="225"><strong>Confusion Matrix</strong>: Highlights model performance in correctly classifying monitored and unmonitored data.</li>
<li class="has-line-data" data-line-start="225" data-line-end="226"><strong>Precision-Recall Curve</strong>: Evaluates precision and recall trade-offs across different thresholds.</li>
<li class="has-line-data" data-line-start="226" data-line-end="228"><strong>ROC Curve</strong>: Demonstrates the model’s ability to distinguish between classes with a high AUC score.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h2 class="code-line" data-line-start=228 data-line-end=229 ><a id=" 33_Open_World_Multi_Classification_Experiments_228"></a>📬 3.3 Open World Multi Classification Experiments</h2>
<p class="has-line-data" data-line-start="230" data-line-end="231">This repository contains experimental code and results for open-world binary classification scenarios. The project explores various techniques to improve classification performance, including feature selection, hyperparameter optimization, and upsampling methods. Use <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature26_BEST.ipynb">open_multi_up_rf_feature26_BEST.ipynb</a> for the final and best-performing model configuration, along with visual insights into data and model performance. The repository is organized into the following files:</p>
<h2 class="code-line" data-line-start=232 data-line-end=233 ><a id="Files_Overview_232"></a>Files Overview</h2>
<h3 class="code-line" data-line-start=234 data-line-end=235 ><a id="1_open_multi_down_feature8_30ipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_down_feature8_30ipynb_234"></a>1) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_down_feature8_30.ipynb">open_multi_down_feature8_30.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="236" data-line-end="237"><strong>Purpose</strong>: experiments with down sampled data, 8 features.</li>
<li class="has-line-data" data-line-start="237" data-line-end="238"><strong>Details</strong>: Includes results for the 8-feature model. (3 models(random forest, gradient boosting, svm)</li>
<li class="has-line-data" data-line-start="238" data-line-end="240"><strong>Outcome</strong>: Demonstrates that the result of down sampling with any model is poor.</li>
</ul>
<h3 class="code-line" data-line-start=240 data-line-end=241 ><a id="2_open_multi_down_rf_feature24_48ipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_down_rf_feature24_48ipynb_240"></a>2) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_down_rf_feature24_48.ipynb">open_multi_down_rf_feature24_48.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="242" data-line-end="243"><strong>Purpose</strong>: experiments with down sampled data, 24 features.</li>
<li class="has-line-data" data-line-start="243" data-line-end="244"><strong>Details</strong>: Includes results for the 24-featured random forest model.</li>
<li class="has-line-data" data-line-start="244" data-line-end="246"><strong>Outcome</strong>: Demonstrates that the result of down sampling with any model and any number of features is poor.</li>
</ul>
<h3 class="code-line" data-line-start=246 data-line-end=247 ><a id="3_open_multi_up_feature_24_xgboostipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_up_feature_24_xgboostipynb_246"></a>3) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_feature_24_xgboost.ipynb">open_multi_up_feature_24_xgboost.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="248" data-line-end="249"><strong>Purpose</strong>: Addresses dataset imbalance using SMOTE upsampling.</li>
<li class="has-line-data" data-line-start="249" data-line-end="251"><strong>Details</strong>: Balances the monitored and unmonitored datasets.</li>
</ul>
<h3 class="code-line" data-line-start=251 data-line-end=252 ><a id="4_open_multi_up_rf_feature24_70ipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_up_rf_feature24_70ipynb_251"></a>4) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature24_70.ipynb">open_multi_up_rf_feature24_70.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="253" data-line-end="254"><strong>Purpose</strong>: Addresses dataset imbalance using SMOTE upsampling.</li>
<li class="has-line-data" data-line-start="254" data-line-end="256"><strong>Details</strong>: Balances the monitored and unmonitored datasets.</li>
</ul>
<h3 class="code-line" data-line-start=256 data-line-end=257 ><a id="5_open_multi_up_rf_feature26_BESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainopenworldmultiopen_multi_up_rf_feature26_BESTipynb_256"></a>5) <a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/open-world/multi/open_multi_up_rf_feature26_BEST.ipynb">open_multi_up_rf_feature26_BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="258" data-line-end="259"><strong>Purpose</strong>: Consolidates all the best experimental results and final configurations.</li>
<li class="has-line-data" data-line-start="259" data-line-end="267"><strong>Details</strong>:
<ul>
<li class="has-line-data" data-line-start="260" data-line-end="261">Combines the expanded 26-feature set, optimized hyperparameters, and balanced dataset.</li>
<li class="has-line-data" data-line-start="261" data-line-end="262">Contains the highest-performing model implementation.</li>
<li class="has-line-data" data-line-start="262" data-line-end="267">Includes detailed result visualizations:
<ul>
<li class="has-line-data" data-line-start="263" data-line-end="264"><strong>Data Distribution Before and After SMOTE</strong>: Shows class balance improvements through upsampling.</li>
<li class="has-line-data" data-line-start="264" data-line-end="265"><strong>Precision-Recall Curve</strong>: Evaluates precision and recall trade-offs across different thresholds.</li>
<li class="has-line-data" data-line-start="265" data-line-end="267"><strong>ROC Curve</strong>: Demonstrates the model’s ability to distinguish between classes with a high AUC score.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h2 class="code-line" data-line-start=267 data-line-end=268 ><a id=" 34_Extra_Credit_267"></a>💌 3.4 Extra Credit</h2>
<h3 class="code-line" data-line-start=269 data-line-end=270 ><a id="extraextra_DF_BESTipynbhttpsgithubcom2024MachineLearningL3L3_Team_Projectblobmainextraextra_DF_BESTipynb_269"></a><a href="https://github.com/2024-MachineLearning-L3/L3_Team_Project/blob/main/extra/extra_DF_BEST.ipynb">extra/extra_DF_BEST.ipynb</a></h3>
<ul>
<li class="has-line-data" data-line-start="271" data-line-end="275">
<p class="has-line-data" data-line-start="271" data-line-end="272"><strong>Purpose</strong>:</p>
<p class="has-line-data" data-line-start="273" data-line-end="274">Classify monitored website traffic using the Deep Fingerprinting (DF) model.</p>
</li>
<li class="has-line-data" data-line-start="275" data-line-end="279">
<p class="has-line-data" data-line-start="275" data-line-end="276"><strong>Details</strong>:</p>
<p class="has-line-data" data-line-start="277" data-line-end="278">Parse network data, extract features, and train a neural network for multi-class classification.</p>
</li>
<li class="has-line-data" data-line-start="279" data-line-end="282">
<p class="has-line-data" data-line-start="279" data-line-end="280"><strong>Outcome</strong>:</p>
<p class="has-line-data" data-line-start="281" data-line-end="282">Achieved high accuracy in identifying website traffic patterns.</p>
</li>
</ul>
<h1 class="code-line" data-line-start=284 data-line-end=285 ><a id="4_Members_284"></a>4. Members</h1>
<p class="has-line-data" data-line-start="286" data-line-end="287">Daye Jang, Hayeon Doh, Sejin Park, Sojeong Lee, Sunho Kwak</p>
