# social-network-analysis

social-network-analysis/

├── data/ # Түүхий болон боловсруулсан өгөгдлийн файлууд 

├── notebooks/ # Шинжилгээний Jupyter тэмдэглэлүүд 

├── scripts/ # SNA-д зориулсан Python скриптүүд 

├── results/ # Дүрслэл зэрэг гаралтын файлууд 

├── README.md # Төслийн ерөнхий мэдээлэл 

├── requirements.txt # Python-ын хамааралтай сангууд



LAB 13. Github тай ажилах 

 Github Лабораторийн заавар
 Нийгмийн Сүлжээний Шинжилгээ
 
Танилцуулга

Github нь кодын хүрээнд хамтран ажиллах болон код хөгжүүлэлтийн хувилбарын 
хяналтад өргөн ашиглагддаг платформ бөгөөд нийгмийн сүлжээний шинжилгээ (SNA)-тэй 
холбоотой төслүүдийг байршуулахад маш тохиромжтой хэрэгсэл юм. Github-ыг ашиглан 
шинжилгээний скриптүүдээ хадгалах, хамтрагчидтайгаа хуваалцах, өгөгдөл боловсруулах, 
дүрслэх платформуудтай нэгтгэх боломжтой. Энэ лабын ажлаар нийгмийн сүлжээний 
шинжилгээ (SNA) төслүүдэд Github ашиглах үндсэн зарчмыг оруулсан.

1. Төслөө Github-д тохируулах
2. 
1.1. Хадгалах газар үүсгэх
   
1. Github руу орно. Github.com
2. 
3. Бүртгэлдээ нэвтэрч эсвэл шинэ бүртгэл үүсгэнэ.
4. 
5. Баруун дээд буланд байрлах + тэмдэг дээр дарж New repository сонгоно.
6. 
7. хадгалах нэрээ оруулна (энэ лаб: social-network-analysis
8. 
9. Public эсвэл Private сонголтыг хийнэ. Мөн README файл ч үүсгэж болно.
10. 
11. Create repository товчийг дарна.
12. 
1.2. Репозиторийг(хадгалах газар) Локалд хуулах
    
Репозиторийг өөрийн компьютерт татаж, хөгжүүлэлтэд бэлтгэнэ

git clone https://github.com/username/social-network-analysis.git

username хэсэгт өөрийн Github хэрэглэгчийн нэрийг оруулна.

2. Төслөө зохион байгуулах
3. 
2.1. Фолдерын бүтэц
   
Төслийн файлуудаа ойлгомжтой, хамтын ажиллагаанд тохирох байдлаар зохион 
байгуулах

social-network-analysis/

├── data/ # Түүхий болон боловсруулсан өгөгдлийн файлууд 

├── notebooks/ # Шинжилгээний Jupyter тэмдэглэлүүд 

├── scripts/ # SNA-д зориулсан Python скриптүүд 

├── results/ # Дүрслэл зэрэг гаралтын файлууд 

├── README.md # Төслийн ерөнхий мэдээлэл 

├── requirements.txt # Python-ын хамааралтай сангууд 
2.2. README файл нэмэх

README.md файлыг засаж дараах мэдээллийг оруулна:
● Төслийн тодорхойлолт
● Орчны тохиргооны заавар

● Шинжилгээ хэрхэн ажиллуулах заавар
Жишээ:
# Нийгмийн Сүлжээний Шинжилгээ 
Энэхүү төсөл нь NetworkX, Matplotlib зэрэг Python сангуудыг ашиглан SNA-г 
хэрэгжүүлсэн жишээг харуулж байна. 
## Орчны тохиргоо 
1. Репозиторийг хуулбарлах: 
 ```bash
 git clone https://github.com/username/social-network-analysis.git
2. Хамааралтай сангуудыг суулгах:
pip install -r requirements.txt
Ашиглах заавар
Шинжилгээний скриптийг ажиллуулах:
python scripts/analyze_network.py
---
## 3. Өгөгдөл нэмэх ба удирдах 
### 3.1. Өгөгдлийн файлуудыг байршуулах 
1. Өгөгдлийн файлуудыг (`CSV` гэх мэт) `data/` фолдерт нэмнэ. 
2. Өөрчлөлтүүдээ commit хийн push хийнэ: 
```bash
git add data/edges.csv
git commit -m "Edge лист өгөгдлийг нэмэв"
git push origin main
3.2. Гадаад эх сурвалжаас өгөгдөл татах
Python скрипт ашиглан өгөгдлийг гадаад эх сурвалжаас шууд татаж авах:
import pandas as pd
url = "https://raw.githubusercontent.com/datasets/sna-datasets/main/edges.csv"
data = pd.read_csv(url)
data.to_csv("data/edges.csv", index=False)
Дээрх скриптийг репозиторид commit хийнэ.
4. Шинжилгээний скрипт бичих, ажиллуулах
4.1. Шинжилгээний скрипт үүсгэх
SNA-д зориулсан Python кодоо скрипт/ хавтсанд хадгална уу:
import networkx as nx
import matplotlib.pyplot as plt
import pandas as pd
# Load data
data = pd.read_csv("../data/edges.csv")
graph = nx.from_pandas_edgelist(data, source='Source', target='Target')
# Visualize the graph
nx.draw(graph, with_labels=True, node_color='skyblue', node_size=1500, edge_color='gray')
plt.show()
# Өгөгдөл ачаалах
өгөгдөл = pd.read_csv("../data/edges.csv")
график = nx.from_pandas_edgelist(өгөгдөл, эх сурвалж='Эх сурвалж', зорилтот='Зорилтот')
# Графикийг дүрслэн харуулах
nx.draw(график, шошготой=Үнэн, node_color='skyblue', node_size=1500, 
edge_color='саарал')
plt.show()
4.2. Скриптийг ажиллуулах
Терминалаас скриптийг ажиллуулна уу:
python scripts/analyze_network.py
5. Хамтын ажиллагаа
5.1. Хамтран ажиллагсад нэмж байна
1. GitHub дээрх репозитор руугаа оч.
2. Settings > Collaborators and Teams дээр дарна уу.
3. Хамтрагчдыг GitHub-д хэрэглэгчийн нэр эсвэл имэйлээр нь нэмнэ үү.
5.2. Салбарлах, татах хүсэлтүүд
1. Шинэ функцүүдэд зориулж салбар үүсгэнэ үү:
git checkout -b онцлог-олон нийтийн илрүүлэх
2. Өөрчлөлтийг хийж, салбарыг түлхэх:
git add scripts/community_detection.py
git commit -m " community detection script-г нэмэх"
git push origin feature-community-detection
3. Өөрчлөлтүүдийг үндсэн салбар руу нэгтгэхийн тулд GitHub дээр татах хүсэлтийг нээнэ 
үү.
6. Үр дүнг нүдээр харуулах
6.1. График хадгалах
Сүлжээний дүрслэлийг үр дүн/ хавтас руу хадгалах:
plt.savefig("../results/network_visualization.png")
6.2. Үр дүнг хуваалцах
git add results/network_visualization.png
git commit -m "Сүлжээний дүрслэлийг нэмэх"
git push origin main
7. Хувилбарын хяналт
7.1. Өөрчлөлтүүдийг хянах
Код болон өгөгдлийн өөрчлөлтийг хянахын тулд Git ашиглана уу:
git status
git diff
7.2. Буцах өөрчлөлтүүд
Хэрэв шаардлагатай бол өмнөх commit рүү буцах:
git checkout commit_hash
8. Ажлаа хуваалцах
8.1. Хадгалах газрыг нийтлэх
Хадгалах газраа олон нийтэд нээлттэй болго:
1. Тохиргоо > Ерөнхий хэсэгт очно уу.
2. "Аюултай бүс" хэсэгт агуулахын харагдах байдлыг public болгож өөрчил.
8.2. Лиценз нэмэх
Бусад хүмүүс таны төслийг хэрхэн ашиглахыг тодруулахын тулд лиценз нэмнэ үү:
1. Add file рүү дарах > (Create New File) Шинэ файл үүсгэх дээр дарна уу.
2. Файлыг LICENSE гэж нэрлээд лицензийн загварыг сонгоно.
9. Ажлын урсгалын жишээ
Алхам алхмаар жишээг тайлбарлах
1. Repository-г клоун хийх: git clone https://github.com/username/social-networkanalysis.git
2. Edge list dataset-ийг data/ хавтас руу нэмэх.
3. scripts/ хавтсанд шинжилгээний скрипт үүсгэж ажиллуулах.
4. Харагдах үр дүнг results/ хавтас руу хадгалах.
5. Өөрчлөлтөө GitHub руу commit хийгээд push хийх:
6. git add .
7. git commit -m "Complete basic social network analysis" git push origin main
Дүгнэлт
GitHub ын гарын авлагыг дагаж мөрдсөнөөр бүтэцлэгдсэн репозитор байгуулах, 
шинжилгээний скрипт бичих, өөрийн ажлыг бусадтай хуваалцах боломжтой. GitHub-ийн 
хувилбар хянах (version control) боломжийг ашиглан ажлын явцыг хянаж, үр дүнтэй 
хамтран ажиллах боломжтой болно.
