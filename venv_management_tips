# Conda + Jupyter 多環境管理教學筆記

## ☑️ 環境規劃概念

| Conda 環境     | 用途                           | 是否裝 Jupyter |
|------------------|----------------------------------|------------------|
| `datasci`        | 資料分析、視覺化、sklearn      | ☑️ 用來啟動 Jupyter |
| `torch-gpu`      | PyTorch + CUDA 深層學習         | ❌ 不用裝 Jupyter    |


## ♻ 第 1 步: 建 datasci 環境 + Jupyter

```bash
conda create -n datasci python=3.10
conda activate datasci
conda install jupyter numpy pandas matplotlib seaborn scikit-learn
```

---

## ♻ 第 2 步: 建 torch-gpu 環境

```bash
conda create -n torch-gpu python=3.10
conda activate torch-gpu
conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia
```

---

## ♻ 第 3 步: 註冊 torch-gpu 環境成 Jupyter kernel

```bash
pip install ipykernel
python -m ipykernel install --user --name torch-gpu --display-name "PyTorch GPU"
```

> 如此一來，你雖然是在 datasci 環境裡啟動 Jupyter notebook，還是可以選擇 PyTorch GPU 或其他 kernel 來執行代碼

---

## 🔢 定義 Jupyter kernel 是什麼？

- Jupyter notebook 是前端啟動器，你從上面選單中選的 kernel (執行環境)
- 其實是 Python 環境已裝 `ipykernel`並已被 Jupyter 註冊

---

## 🔍 常用操作指令

### 查看已註冊 kernel 列表
```bash
jupyter kernelspec list
```

### 刪除 kernel
```bash
jupyter kernelspec remove torch-gpu
```

### 查看所有 conda 環境
```bash
conda env list
```

### 查看環境內的套件
```bash
conda list -n torch-gpu
```

### 從 pip 環境載入 kernel (venv 也可)
```bash
python -m ipykernel install --user --name=myenv --display-name "My Custom Env"
```

---

## 🚀 結合 VSCode 開 Jupyter Notebook
- VSCode 會自動讀取你的 kernel
- 於 VSCode notebook 頁面可以選擇 kernel
- 在不同環境下編譯不同的工程

---

## ☑️ 結論

- 將 Jupyter 裝在一個主環境 (datasci) 就好
- 其他環境只要註冊 kernel 就可以裡外執行
- 根據用途分環境，維持狀態清楚、隱性性高

