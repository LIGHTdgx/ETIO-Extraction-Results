# ETIO-Extraction-Results
### 该项目包含了论文“Event-based Threat Intelligence Ontology Model”中的部分数据

1）**concept.txt**包含了约简后的形式概念集（选取keys=4时）

2）**Extraction Results.txt**包含了对8篇“白象”组织的APT报告进行信息抽取后的结果

### 下面是信息抽取过程中使用的*prompt*示例 
`prompt='Now that you are an expert in the field of cybersecurity, please extract (concepts,properties) tuple related to the cyber attack from the following text, and represent them line-by-line in json format.\n text:'`

**设置限定词进行多轮抽取**
`prompt_list=[['Handware','LINK','Service','Data'],['personal','organization'],['Destruction','Data Theft', 'Control'],['Demonstrating strength','political purpose'],['Reconnaissance','Resource Development','Initial Acess','Execution','Persistence','Defense Evasion','Discovery','Collection','Command and Control','Exfiltration'],['patching','backing up files','shutting down computers','installing/updating antivirus software','disconnecting from the Internet','improving email precautions']]
prompt = "Given the list:{},for each word in list, please tell me if the following text reflect these words,and represent it in JSON format:\n".format(prompt_list[i])`

**单轮抽取**
`prompt = "Now you are a cybersecurity expert, given an entity list: [Timestamp, Target Asset Name, Target Asset Owner Name, Vulnerability ID, Network Tool Name]\n\nPlease tell me what entity might be included in the following text, represent it all in JSON format:\n"`
