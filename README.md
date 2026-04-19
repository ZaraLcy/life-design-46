# 46歲的人生設計

A5 商業書 pilot。使用 `htlin222/bestseller` 模板：Quarto + Typst、APA CSL、CrossRef DOI 驗證、繁中 A5 內頁排版，字型改用芫荽體（Typst family：`芫荽`）。

## 書籍定位

**書名**：《46歲的人生設計》

**副標**：不是重來一次，而是重新配置你的時間、身體、關係與現金流

這不是中年勵志書，而是寫給 40+ 高責任族群的人生產品經理手冊。核心主張：中年不是重新開始，而是重新配置。全書預計約 10 章、A5 約 100 頁。

## Pilot 內容

- `index.qmd`：前言〈為什麼是 46 歲〉
- `01.qmd`：第一章〈你不是卡住，你是進入第二套作業系統〉
- `02.qmd`：第二章〈46歲的人生資產負債表〉
- `ch-outlines.md`：全書章節規畫
- `references.bib`：pilot DOI 文獻庫

## 渲染

```bash
quarto render cover.qmd --to typst
quarto render book.qmd --to typst
python3 scripts/build-toc.py
quarto render toc.qmd --to typst
```

輸出會在 `_book/`。

## HTML / GitHub Pages

```bash
quarto render web.qmd --to html
```

輸出會產生 `_book/index.html`，可直接部署到 GitHub Pages。此版本使用 `styles.css` 做商業書閱讀版設計，並使用 `assets/cover.png` 作為首頁書封視覺。

已包含 GitHub Actions workflow：`.github/workflows/deploy-pages.yml`。推到 `main` 後，到 GitHub repository 的 Pages 設定選擇 GitHub Actions 作為來源即可自動部署。

## 驗證引用

```bash
bash scripts/verify-crossref.sh references.bib verification-report.md
```

## 寫作規格

每章固定包含：

- 一個中年真實場景
- 一個研究支點
- 一個反直覺判斷
- 一個可操作工具
- 一個「今晚就能做」的完成信號

語氣要求：科學、理性、務實，但維持商業書可讀性。避免裸辭神話、熱情神話、財務自由神話，以及把結構限制簡化成個人心態問題。
