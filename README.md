鳶尾花資料集分類與 PCA 視覺化
此專案實現了使用 K 最近鄰居演算法（KNN）對鳶尾花（Iris）資料集進行分類，並透過主成分分析（PCA）進行資料視覺化。

概述
資料準備：

載入 Iris 資料集，並將其分為訓練集和測試集。
模型訓練：

使用 
𝐾
=
3
K=3 的 KNN 模型，基於訓練集進行訓練。
模型評估：

使用測試集進行預測，並以分類報告及準確率評估模型表現。
PCA 視覺化：

將資料維度從 4 維降至 2 維，以便進行分佈可視化。
環境需求
本專案需以下 Python 套件：

numpy
pandas
matplotlib
scikit-learn
功能說明
1. K 最近鄰居（KNN）模型
使用 KNN 分類器，參數設定如下：
鄰居數量（n_neighbors）：3
訓練集與測試集比例：80% 訓練，20% 測試
分類器對測試集資料進行預測，並使用以下指標進行評估：
準確率
分類報告（精確度、召回率、F1 分數）
2. PCA 視覺化
使用 PCA 將原始 4 維特徵壓縮為 2 維。
繪製散佈圖，顯示不同鳶尾花種類的分佈情況。
使用方法
執行程式
載入資料並分割為訓練集與測試集：

python
複製程式碼
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
訓練 KNN 模型：

python
複製程式碼
knn = KNeighborsClassifier(n_neighbors=3)
knn.fit(X_train, y_train)
評估模型：

python
複製程式碼
accuracy = accuracy_score(y_test, y_pred)
print(f"準確率: {accuracy}")
PCA 資料降維：

python
複製程式碼
pca = PCA(n_components=2)
X_pca = pca.fit_transform(X)
繪製視覺化結果：

python
複製程式碼
plt.scatter(X_pca[y == i, 0], X_pca[y == i, 1])
plt.title("鳶尾花資料集視覺化（PCA）")
結果
模型準確率：輸出分類準確率（例如：準確率: 0.97）。
分類報告：顯示每個類別的精確度、召回率與 F1 分數。
PCA 視覺化：呈現 2D 散佈圖，展示不同鳶尾花類別的分佈。
