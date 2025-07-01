<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Optimal Topic Number Analysis - Trauma Nursing Research</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/chartjs-adapter-date-fns/dist/chartjs-adapter-date-fns.bundle.min.js"></script>
    <style>
        body {
            font-family: 'Times New Roman', serif;
            margin: 20px;
            background-color: #f8f9fa;
        }
        .container {
            max-width: 1400px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 40px;
            font-size: 32px;
            border-bottom: 3px solid #3498db;
            padding-bottom: 15px;
        }
        h2 {
            color: #34495e;
            border-left: 4px solid #3498db;
            padding-left: 15px;
            margin-top: 40px;
            font-size: 24px;
        }
        .optimal-summary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 25px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
        }
        .summary-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        .summary-item {
            background: rgba(255,255,255,0.2);
            padding: 15px;
            border-radius: 10px;
        }
        .summary-value {
            font-size: 2em;
            font-weight: bold;
            display: block;
        }
        .summary-label {
            font-size: 0.9em;
            opacity: 0.9;
        }
        .chart-container {
            margin: 30px 0;
            padding: 25px;
            border: 2px solid #ecf0f1;
            border-radius: 10px;
            background-color: #fdfdfd;
        }
        .chart-title {
            text-align: center;
            font-weight: bold;
            margin-bottom: 25px;
            color: #2c3e50;
            font-size: 18px;
        }
        .evaluation-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            font-size: 14px;
        }
        .evaluation-table th, .evaluation-table td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: center;
        }
        .evaluation-table th {
            background-color: #34495e;
            color: white;
            font-weight: bold;
        }
        .optimal-row {
            background-color: #2ecc71;
            color: white;
            font-weight: bold;
        }
        .high-score {
            background-color: #e8f5e8;
        }
        .medium-score {
            background-color: #fff3cd;
        }
        .low-score {
            background-color: #f8d7da;
        }
        .topic-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        .topic-card {
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 20px;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }
        .topic-title {
            font-weight: bold;
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 16px;
        }
        .topic-keywords {
            font-size: 14px;
            color: #34495e;
            line-height: 1.6;
        }
        .trend-analysis {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        .trend-card {
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 20px;
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
        }
        .trend-title {
            font-weight: bold;
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 16px;
        }
        .trend-stats {
            font-size: 14px;
            color: #34495e;
        }
        .trend-up {
            color: #27ae60;
            font-weight: bold;
        }
        .trend-down {
            color: #e74c3c;
            font-weight: bold;
        }
        .trend-stable {
            color: #f39c12;
            font-weight: bold;
        }
        .insights-box {
            background-color: #ecf0f1;
            border-left: 5px solid #3498db;
            padding: 20px;
            margin: 20px 0;
            border-radius: 5px;
        }
        .insights-title {
            font-weight: bold;
            color: #2c3e50;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Optimal Topic Number Analysis for Trauma Nursing Research</h1>
        
        <!-- 최적 토픽 수 요약 -->
        <div class="optimal-summary">
            <h3>Optimal Topic Analysis Results</h3>
            <div class="summary-grid">
                <div class="summary-item">
                    <span class="summary-value">19</span>
                    <span class="summary-label">Optimal Topics</span>
                </div>
                <div class="summary-item">
                    <span class="summary-value">-0.765</span>
                    <span class="summary-label">Best Coherence</span>
                </div>
                <div class="summary-item">
                    <span class="summary-value">379.1</span>
                    <span class="summary-label">Best Perplexity</span>
                </div>
                <div class="summary-item">
                    <span class="summary-value">423</span>
                    <span class="summary-label">Documents Analyzed</span>
                </div>
            </div>
        </div>

        <!-- 모델 평가 지표 차트 -->
        <h2>1. Model Evaluation Metrics</h2>
        <div class="chart-container">
            <div class="chart-title">Coherence and Perplexity Scores by Number of Topics</div>
            <canvas id="evaluationChart" width="1200" height="600"></canvas>
        </div>

        <!-- 평가 결과 테이블 -->
        <h2>2. Detailed Evaluation Results</h2>
        <div class="chart-container">
            <div class="chart-title">Comparison of Topic Numbers (10-20)</div>
            <table class="evaluation-table" id="evaluationTable">
                <thead>
                    <tr>
                        <th>Topics</th>
                        <th>Coherence</th>
                        <th>Perplexity</th>
                        <th>Combined Score</th>
                        <th>Rank</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- 동적으로 생성됨 -->
                </tbody>
            </table>
        </div>

        <!-- 최적 토픽 상세 정보 -->
        <h2>3. Optimal Topic Details</h2>
        <div class="topic-grid" id="optimalTopics">
            <!-- 동적으로 생성됨 -->
        </div>

        <!-- 연도별 토픽 분포 추세 -->
        <h2>4. Temporal Topic Distribution</h2>
        <div class="chart-container">
            <div class="chart-title">Topic Proportions Over Time (Optimal Model)</div>
            <canvas id="temporalChart" width="1200" height="600"></canvas>
        </div>

        <!-- 추세 분석 -->
        <h2>5. Topic Trend Analysis</h2>
        <div class="trend-analysis" id="trendAnalysis">
            <!-- 동적으로 생성됨 -->
        </div>

        <!-- 인사이트 -->
        <div class="insights-box">
            <div class="insights-title">Key Research Insights:</div>
            <div id="insights">
                <!-- 동적으로 생성됨 -->
            </div>
        </div>
    </div>

    <script>
        // 데이터 설정
        const evaluationData = {"topic_numbers": [10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20], "coherence_scores": [-1.0696074795153296, -1.053411704584378, -0.9426347980105682, -1.002812475444565, -0.9431147882261416, -0.8901661314702934, -0.9845037579228826, -0.856699072068665, -0.7782340076746406, -0.764521088457944, -0.83698263927231], "perplexity_scores": [489.73021532338817, 472.51351032378744, 454.5380107637885, 451.0604082722281, 427.89859283965103, 413.048914555624, 408.85374866216745, 396.9922689701693, 390.0791829127761, 379.0862755686168, 383.2517837742112], "norm_perplexity_scores": [0.0, 0.1556045910671604, 0.31806716786837874, 0.3494977414657048, 0.5588342445214741, 0.6930456465823509, 0.7309615586761773, 0.8381656199043628, 0.9006460962206904, 1.0, 0.9623521341085041], "combined_scores": [0.0, 0.08384148273282664, 0.38675034291772553, 0.25810592194742416, 0.4578791609693828, 0.6196296777528829, 0.4145531757671303, 0.7399535641552168, 0.9387304672314298, 1.0, 0.8224475341457563], "detailed_results": [{"topics": 10, "coherence": -1.0696074795153296, "perplexity": 489.73021532338817, "combined_score": 0.0, "rank": 11}, {"topics": 11, "coherence": -1.053411704584378, "perplexity": 472.51351032378744, "combined_score": 0.08384148273282664, "rank": 10}, {"topics": 12, "coherence": -0.9426347980105682, "perplexity": 454.5380107637885, "combined_score": 0.38675034291772553, "rank": 8}, {"topics": 13, "coherence": -1.002812475444565, "perplexity": 451.0604082722281, "combined_score": 0.25810592194742416, "rank": 9}, {"topics": 14, "coherence": -0.9431147882261416, "perplexity": 427.89859283965103, "combined_score": 0.4578791609693828, "rank": 6}, {"topics": 15, "coherence": -0.8901661314702934, "perplexity": 413.048914555624, "combined_score": 0.6196296777528829, "rank": 5}, {"topics": 16, "coherence": -0.9845037579228826, "perplexity": 408.85374866216745, "combined_score": 0.4145531757671303, "rank": 7}, {"topics": 17, "coherence": -0.856699072068665, "perplexity": 396.9922689701693, "combined_score": 0.7399535641552168, "rank": 4}, {"topics": 18, "coherence": -0.7782340076746406, "perplexity": 390.0791829127761, "combined_score": 0.9387304672314298, "rank": 2}, {"topics": 19, "coherence": -0.764521088457944, "perplexity": 379.0862755686168, "combined_score": 1.0, "rank": 1}, {"topics": 20, "coherence": -0.83698263927231, "perplexity": 383.2517837742112, "combined_score": 0.8224475341457563, "rank": 3}], "optimal_topics": 19, "optimal_coherence": -0.764521088457944, "optimal_perplexity": 379.0862755686168};
        const bestTopics = [{"name": "pain + protocol + time", "keywords": ["pain", "protocol", "time", "management", "decrease", "increase", "opioid", "leadership", "implement", "medication"]}, {"name": "discharge + after + during", "keywords": ["discharge", "after", "during", "home", "from", "management", "intervention", "between", "include", "report"]}, {"name": "physical + inform + abuse", "keywords": ["physical", "inform", "abuse", "from", "recovery", "assessment", "include", "student", "attitude", "cognitive"]}, {"name": "satisfaction + stress + burnout", "keywords": ["satisfaction", "stress", "burnout", "professional", "level", "fatigue", "secondary", "report", "experience", "among"]}, {"name": "after + icu + quality", "keywords": ["after", "icu", "quality", "early", "improve", "month", "intervention", "reduce", "perception", "head"]}, {"name": "blood + transfusion + mtp", "keywords": ["blood", "transfusion", "mtp", "receive", "txa", "level", "massive", "hemorrhage", "resuscitation", "mortality"]}, {"name": "old + fall + prevention", "keywords": ["old", "fall", "prevention", "risk", "falls", "adult", "frailty", "spinal", "factor", "cord"]}, {"name": "training + blunt + procedure", "keywords": ["training", "blunt", "procedure", "exposure", "evaluate", "resuscitation", "education", "evaluation", "postintervention", "organ"]}, {"name": "stress + disorder + posttraumatic", "keywords": ["stress", "disorder", "posttraumatic", "risk", "depression", "screen", "ptsd", "critical", "psychological", "anxiety"]}, {"name": "fracture + infectionion + associate", "keywords": ["fracture", "infectionion", "associate", "hip", "catheter", "complication", "uti", "ventilator", "rib", "pneumonia"]}, {"name": "screen + alcohol + compliance", "keywords": ["screen", "alcohol", "compliance", "intervention", "evaluation", "implementation", "implement", "level", "electronic", "increase"]}, {"name": "iss + mortality + high", "keywords": ["iss", "mortality", "high", "severity", "icu", "complication", "los", "registry", "compare", "between"]}, {"name": "child + violence + prevention", "keywords": ["child", "violence", "prevention", "safety", "vehicle", "motor", "passenger", "from", "restraint", "mvc"]}, {"name": "team + improvement + implementation", "keywords": ["team", "improvement", "implementation", "develop", "performance", "process", "provide", "communication", "identify", "improve"]}, {"name": "family + need + education", "keywords": ["family", "need", "education", "provide", "support", "caregiver", "educational", "death", "response", "experience"]}, {"name": "simulation + prehospital + venous", "keywords": ["simulation", "prehospital", "venous", "device", "increase", "virtual", "thromboembolism", "compression", "cervical", "spine"]}, {"name": "pediatric + child + education", "keywords": ["pediatric", "child", "education", "provide", "identify", "center", "need", "from", "registry", "concussion"]}, {"name": "admission + geriatric + tbi", "keywords": ["admission", "geriatric", "tbi", "score", "than", "los", "compare", "between", "age", "admit"]}, {"name": "level + center + from", "keywords": ["level", "center", "from", "time", "activation", "american", "rural", "surgeon", "college", "transfer"]}];
        const yearlyData = {"years": [2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023, 2024], "topics": [{"values": [6.514964156821458, 4.7422101498174145, 7.49562564502219, 4.972115869442098, 5.019756307408955, 3.9944423626861467, 3.266754024300405, 2.942231434281724, 1.741366674214106, 2.7334148161090823]}, {"values": [8.06516101826672, 6.026505195160485, 9.842796229077813, 7.655801077214007, 10.475221578738585, 4.946797258502178, 6.994186888049684, 6.345276830401058, 8.715786183614311, 6.343990551785089]}, {"values": [2.1973351254093654, 7.078454227461541, 3.7008078131178532, 3.4735285993792795, 5.268412573450617, 4.109165971711915, 4.694017431481018, 5.180910240124041, 3.545584296512606, 3.2275881703700633]}, {"values": [1.3737690835740741, 3.84651714258369, 7.069837355741646, 5.178035458278287, 1.7660953629818918, 7.156454425801632, 6.546518074059909, 8.234286470372417, 2.906836144670327, 5.52339276163123]}, {"values": [9.25488361273073, 6.534944181497697, 2.3894283995918832, 7.940931999003936, 5.1079375075671605, 3.961521239712119, 3.613065843073145, 1.5822887652683015, 6.633485360350623, 6.6869130137258495]}, {"values": [1.216661590884024, 2.821918201808465, 5.751004639404343, 4.3790068657290915, 5.60198337849883, 5.574216823243581, 2.8262744984180364, 2.2153315256870347, 5.522887354693878, 5.165344649388794]}, {"values": [2.033911933296299, 2.035319295427785, 3.4761916690613766, 3.583729670963456, 3.2534040404139897, 2.180874212346593, 5.973732097772524, 5.5239691445529475, 3.960577139602954, 3.649739995614883]}, {"values": [5.3507562306904966, 4.261986139081372, 3.948237948743932, 3.08572148655475, 1.884778892095817, 3.0336626077920554, 3.8358929242456754, 6.815172194798643, 6.728444712421723, 4.259745499496017]}, {"values": [3.5867118760876884, 1.764235873736205, 2.9313687519935603, 1.4750787270380927, 3.136010065968447, 4.328910870669155, 3.857792378065454, 6.0156486326583885, 4.270778491239983, 3.6540472973564886]}, {"values": [6.001888133974104, 1.569349883198232, 2.3755402128082386, 7.116365520358584, 0.9927850785380199, 7.7176407941841125, 7.354115248492114, 2.5008511840926313, 3.5474994793551122, 4.9120764545768445]}, {"values": [3.6385520993101492, 5.000183604131877, 4.563722506722119, 5.627730934387984, 3.9107016030753594, 5.822612156910182, 2.813137111646399, 1.6866791209848015, 6.28077040175831, 5.641603602373981]}, {"values": [3.7797523413180794, 3.6494718565243898, 7.000530242867351, 5.8930765909409635, 9.540810932088748, 7.432386842910689, 8.387138902866175, 9.90253616077962, 2.9949961849018614, 3.3812380345094]}, {"values": [1.9675473437468394, 6.584825978048399, 3.9430547927388955, 4.460651367418849, 2.7904285069845036, 3.0161797905866785, 3.449753940390151, 5.304363453741652, 5.626955707499473, 2.9596683028309037]}, {"values": [16.897285260748454, 11.255202010556086, 13.083153552372048, 10.897835662270047, 14.400175246336696, 7.762899033475704, 8.520679164272165, 9.79579966419052, 11.048359641037141, 8.927207818456209]}, {"values": [7.459897522727692, 11.381911951930137, 7.486397131595841, 6.158583960919432, 8.698082212661632, 6.508009670273086, 3.1071974686497255, 6.517873714947251, 3.9258969343494625, 6.757408054145292]}, {"values": [2.3523104172682507, 2.114752616039188, 4.947614888606854, 2.9358678161929532, 0.7019148665003648, 2.24148269958037, 3.194112339592832, 4.074723901167355, 3.076165569005118, 8.028301729348597]}, {"values": [4.7356980282964996, 6.2173839302440435, 1.2549119550832128, 3.9313363626211935, 5.508427319427788, 3.855274515332819, 5.667358714367307, 3.443164417712769, 5.954473900285618, 5.8561640840932165]}, {"values": [9.877700455518374, 4.767253892589637, 4.981596442663683, 6.0332818983134935, 4.8108244131742905, 7.857996907062055, 7.138570795568265, 5.479400304734581, 5.687203866631026, 2.98776172465071]}, {"values": [3.6952137693307052, 8.347573870163355, 3.7581798227871555, 5.2013201329735015, 7.132250114088294, 8.499471817218923, 8.759702154689013, 6.439492839504256, 7.831931957856364, 9.304393439537346]}]};
        const trendAnalysis = [{"change_rate": -0.11716796940868925, "peak_year": 2017, "avg_proportion": 4.342288144010358}, {"change_rate": -0.017412684309674138, "peak_year": 2019, "avg_proportion": 7.541152281080993}, {"change_rate": -0.007926195266047832, "peak_year": 2016, "avg_proportion": 4.24758044490183}, {"change_rate": 0.05631143668247716, "peak_year": 2022, "avg_proportion": 4.96017422796951}, {"change_rate": -0.0458028091807403, "peak_year": 2015, "avg_proportion": 5.370539992252144}, {"change_rate": 0.04733527615288291, "peak_year": 2017, "avg_proportion": 4.107462952775608}, {"change_rate": 0.07536053605019576, "peak_year": 2021, "avg_proportion": 3.5671449199052807}, {"change_rate": 0.03532213678388122, "peak_year": 2022, "avg_proportion": 4.320439863592048}, {"change_rate": 0.07253614481027372, "peak_year": 2022, "avg_proportion": 3.5020582964813465}, {"change_rate": 0.016638033946935124, "peak_year": 2020, "avg_proportion": 4.4088111989578}, {"change_rate": 0.008183724099291917, "peak_year": 2023, "avg_proportion": 4.498569314130116}, {"change_rate": 0.01145946311140068, "peak_year": 2022, "avg_proportion": 6.196193808970728}, {"change_rate": 0.009405375764888757, "peak_year": 2016, "avg_proportion": 4.010342918398634}, {"change_rate": -0.05565131569671354, "peak_year": 2015, "avg_proportion": 11.258859705371508}, {"change_rate": -0.06657751943820998, "peak_year": 2016, "avg_proportion": 6.800125862219955}, {"change_rate": 0.10038289466912821, "peak_year": 2024, "avg_proportion": 3.366724684330188}, {"change_rate": 0.02968671665124143, "peak_year": 2016, "avg_proportion": 4.642419322746447}, {"change_rate": -0.04748914217992528, "peak_year": 2015, "avg_proportion": 5.962159070090611}, {"change_rate": 0.06355204891853969, "peak_year": 2024, "avg_proportion": 6.89695299181489}];

        // 색상 팔레트
        const colors = [
            '#FF6384', '#36A2EB', '#FFCE56', '#4BC0C0', '#9966FF',
            '#FF9F40', '#FF6384', '#C9CBCF', '#4BC0C0', '#FF6384',
            '#36A2EB', '#FFCE56', '#4BC0C0', '#9966FF', '#FF9F40',
            '#FF6384', '#C9CBCF', '#4BC0C0', '#FF6384', '#36A2EB'
        ];

        // 1. 모델 평가 차트
        const ctx1 = document.getElementById('evaluationChart').getContext('2d');
        new Chart(ctx1, {
            type: 'line',
            data: {
                labels: evaluationData.topic_numbers,
                datasets: [
                    {
                        label: 'Coherence Score',
                        data: evaluationData.coherence_scores,
                        borderColor: '#e74c3c',
                        backgroundColor: 'rgba(231, 76, 60, 0.1)',
                        yAxisID: 'y',
                        tension: 0.4,
                        pointRadius: 6,
                        pointHoverRadius: 8,
                        borderWidth: 3
                    },
                    {
                        label: 'Perplexity Score (Normalized)',
                        data: evaluationData.norm_perplexity_scores,
                        borderColor: '#3498db',
                        backgroundColor: 'rgba(52, 152, 219, 0.1)',
                        yAxisID: 'y',
                        tension: 0.4,
                        pointRadius: 6,
                        pointHoverRadius: 8,
                        borderWidth: 3
                    },
                    {
                        label: 'Combined Score',
                        data: evaluationData.combined_scores,
                        borderColor: '#2ecc71',
                        backgroundColor: 'rgba(46, 204, 113, 0.1)',
                        yAxisID: 'y',
                        tension: 0.4,
                        pointRadius: 8,
                        pointHoverRadius: 10,
                        borderWidth: 4
                    }
                ]
            },
            options: {
                responsive: true,
                interaction: {
                    intersect: false,
                    mode: 'index'
                },
                scales: {
                    x: {
                        title: {
                            display: true,
                            text: 'Number of Topics',
                            font: {
                                size: 14,
                                weight: 'bold'
                            }
                        }
                    },
                    y: {
                        type: 'linear',
                        display: true,
                        position: 'left',
                        title: {
                            display: true,
                            text: 'Score',
                            font: {
                                size: 14,
                                weight: 'bold'
                            }
                        }
                    }
                },
                plugins: {
                    legend: {
                        position: 'top',
                        labels: {
                            font: {
                                size: 12
                            }
                        }
                    },
                    tooltip: {
                        callbacks: {
                            title: function(context) {
                                return 'Topics: ' + context[0].label;
                            },
                            label: function(context) {
                                return context.dataset.label + ': ' + context.parsed.y.toFixed(3);
                            }
                        }
                    }
                }
            }
        });

        // 2. 평가 테이블 생성
        function createEvaluationTable() {
            const tbody = document.querySelector('#evaluationTable tbody');
            
            evaluationData.detailed_results.forEach((result, index) => {
                const row = document.createElement('tr');
                if (result.rank === 1) {
                    row.className = 'optimal-row';
                } else if (result.rank <= 3) {
                    row.className = 'high-score';
                } else if (result.rank <= 6) {
                    row.className = 'medium-score';
                } else {
                    row.className = 'low-score';
                }
                
                row.innerHTML = `
                    <td>${result.topics}</td>
                    <td>${result.coherence.toFixed(4)}</td>
                    <td>${result.perplexity.toFixed(2)}</td>
                    <td>${result.combined_score.toFixed(4)}</td>
                    <td>${result.rank}</td>
                `;
                tbody.appendChild(row);
            });
        }

        // 3. 최적 토픽 상세 정보
        function createOptimalTopics() {
            const container = document.getElementById('optimalTopics');
            
            bestTopics.forEach((topic, index) => {
                const card = document.createElement('div');
                card.className = 'topic-card';
                
                card.innerHTML = `
                    <div class="topic-title">Topic ${index + 1}: ${topic.name}</div>
                    <div class="topic-keywords">
                        <strong>Top Keywords:</strong><br>
                        ${topic.keywords.map((word, i) => `${i+1}. ${word}`).join('<br>')}
                    </div>
                `;
                container.appendChild(card);
            });
        }

        // 4. 연도별 토픽 분포 차트
        if (yearlyData && yearlyData.years) {
            const ctx4 = document.getElementById('temporalChart').getContext('2d');
            new Chart(ctx4, {
                type: 'line',
                data: {
                    labels: yearlyData.years,
                    datasets: yearlyData.topics.map((topic, index) => ({
                        label: `Topic ${index + 1}`,
                        data: topic.values,
                        borderColor: colors[index % colors.length],
                        backgroundColor: colors[index % colors.length] + '20',
                        fill: false,
                        tension: 0.4,
                        pointRadius: 4,
                        pointHoverRadius: 6
                    }))
                },
                options: {
                    responsive: true,
                    interaction: {
                        intersect: false,
                        mode: 'index'
                    },
                    scales: {
                        x: {
                            title: {
                                display: true,
                                text: 'Year',
                                font: {
                                    size: 14,
                                    weight: 'bold'
                                }
                            }
                        },
                        y: {
                            title: {
                                display: true,
                                text: 'Topic Proportion (%)',
                                font: {
                                    size: 14,
                                    weight: 'bold'
                                }
                            },
                            beginAtZero: true
                        }
                    },
                    plugins: {
                        legend: {
                            position: 'right',
                            labels: {
                                font: {
                                    size: 10
                                },
                                boxWidth: 12
                            }
                        }
                    }
                }
            });
        }

        // 5. 추세 분석 생성
        function createTrendAnalysis() {
            if (!trendAnalysis || trendAnalysis.length === 0) return;
            
            const container = document.getElementById('trendAnalysis');
            
            trendAnalysis.forEach((trend, index) => {
                const card = document.createElement('div');
                card.className = 'trend-card';
                
                let trendClass = 'trend-stable';
                let trendText = 'Stable';
                if (trend.change_rate > 0.1) {
                    trendClass = 'trend-up';
                    trendText = 'Increasing';
                } else if (trend.change_rate < -0.1) {
                    trendClass = 'trend-down';
                    trendText = 'Decreasing';
                }
                
                card.innerHTML = `
                    <div class="trend-title">Topic ${index + 1}</div>
                    <div class="trend-stats">
                        <div>Trend: <span class="${trendClass}">${trendText}</span></div>
                        <div>Change Rate: <span class="${trendClass}">${(trend.change_rate * 100).toFixed(1)}%</span></div>
                        <div>Peak Year: ${trend.peak_year}</div>
                        <div>Avg Proportion: ${trend.avg_proportion.toFixed(1)}%</div>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        // 6. 인사이트 생성
        function generateInsights() {
            const insights = [];
            
            insights.push(`<strong>Optimal Topic Number:</strong> Our analysis determined that ${evaluationData.optimal_topics} topics provide the best balance between coherence (${evaluationData.optimal_coherence.toFixed(3)}) and model complexity.`);
            
            insights.push(`<strong>Model Quality:</strong> The optimal model achieved a coherence score of ${evaluationData.optimal_coherence.toFixed(3)}, indicating good topic interpretability and semantic coherence.`);
            
            if (trendAnalysis && trendAnalysis.length > 0) {
                const fastestGrowing = trendAnalysis.reduce((max, trend, index) => 
                    trend.change_rate > max.change_rate ? {...trend, index} : max
                );
                insights.push(`<strong>Emerging Research Area:</strong> Topic ${fastestGrowing.index + 1} shows the fastest growth trend with ${(fastestGrowing.change_rate * 100).toFixed(1)}% annual increase, suggesting an emerging area of research interest.`);
                
                const mostStable = trendAnalysis.reduce((min, trend, index) => 
                    Math.abs(trend.change_rate) < Math.abs(min.change_rate) ? {...trend, index} : min
                );
                insights.push(`<strong>Core Research Area:</strong> Topic ${mostStable.index + 1} demonstrates the most stability over time, indicating a consistently important research domain in trauma nursing.`);
            }
            
            insights.push(`<strong>Research Recommendation:</strong> The ${evaluationData.optimal_topics}-topic model provides optimal granularity for understanding research themes without excessive fragmentation, making it ideal for systematic reviews and research trend analysis.`);
            
            document.getElementById('insights').innerHTML = insights.join('<br><br>');
        }

        // 초기화
        createEvaluationTable();
        createOptimalTopics();
        createTrendAnalysis();
        generateInsights();
    </script>
</body>
</html>
