<div align="center">
  <h2 style="font-size: 36px; font-weight: bold; color: #333;">From Scratch to Submission: A Complete Guide to Academic Conference Paper Writing</h2>
  <h4 style="font-size: 20px; color: #777; font-style: italic;">“Research is to see what everybody else has seen and to think what nobody else has thought.” — Albert Szent-Györgyi</h4>
</div>

<div align="center" style="margin-top: 20px;">
  <!-- GitHub Stars Badge -->
  <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/KejiaZhang-Robust/Academic-paper-writing?style=social" style="margin: 0 0px;">
  <!-- License Badge -->
  <img alt="GitHub License" src="https://img.shields.io/github/license/KejiaZhang-Robust/Academic-paper-writing?style=flat-square" style="margin: 0 0px;">
  <!-- Documentation Badge -->
  <img alt="Documentation" src="https://img.shields.io/badge/docs-available-brightgreen?style=flat-square" style="margin: 0 0px;">
</div>

---

# 📜 LaTeX Basics for Academic Paper Writing

## 📥 1. Downloading Conference Templates

To begin, download the official LaTeX template from the target conference website. Look for the “Call for Papers” section, where you’ll find Author Instructions and Style Files.

For Overleaf users, upload the template directly to your Overleaf project:
🔗 [Overleaf](https://www.overleaf.com/)

## 📂 2. Organizing Your LaTeX Project

A well-structured LaTeX project enhances readability and simplifies collaboration. Here’s a recommended folder structure:

```
📁 Project Root
 ├── 📁 Figures/        # Stores all figure files (PNG, PDF, EPS)
 ├── 📁 Tables/         # Stores LaTeX tables
 ├── 📁 Sections/       # Stores individual sections as separate .tex files
 │    ├── 0_Teaser.tex
 │    ├── 1_Introduction.tex
 │    ├── 2_Related_Work.tex
 │    ├── 3_Method.tex
 │    ├── 4_Experiment.tex
 │    ├── 5_Conclusion.tex
 │    ├── 6_Appendix.tex
 ├── 📄 references.bib   # Bibliography file for citations
 ├── 📄 main.tex         # Main LaTeX file organizing the paper
 ├── 📄 template.cls     # Conference template class file
 ├── 📄 style.sty        # Additional formatting files (if provided)
 ├── 📄 Additional Files
```

Best Practices:

- ✅ Use \input{} to modularize sections instead of writing everything in main.tex.
- ✅ Keep figures and tables in dedicated folders for better file management.
- ✅ Follow the conference’s required file structure (e.g., supplementary materials).

## 📚 3. Citation and Reference Formatting

For conference papers, use @inproceedings, while journal papers should be formatted as @article. Maintain a consistent citation style and use pre-defined conference abbreviations for clarity.

BibTeX Example:

```
@inproceedings{example2024,
  author    = {John Doe and Jane Smith},
  title     = {A Novel Approach to XYZ},
  booktitle = CVPR,
  year      = {2024}
}

@article{example_journal,
  author  = {John Doe and Jane Smith},
  title   = {Deep Learning for XYZ},
  journal = {IEEE TPAMI},
  volume  = {42},
  number  = {4},
  pages   = {123-135},
  year    = {2024}
}
```

Conference and Journal Name Shortcuts

```
@String(PAMI  = {IEEE TPAMI})
@String(IJCV  = {IJCV})
@String(CVPR  = {CVPR})
@String(ICML  = {ICML})
@String(ICCV  = {ICCV})
@String(ECCV  = {ECCV})
@String(NIPS  = {NeurIPS})
@String(ICPR  = {ICPR})
@String(ICML  = {ICML})
@String(BMVC  =	{BMVC})
@String(TOG   = {ACM TOG})
@String(TIP   = {IEEE TIP})
@String(TVCG  = {IEEE TVCG})
@String(TCSVT = {IEEE TCSVT})
@String(TMM   =	{IEEE TMM})
@String(ACMMM = {ACM MM})
@String(ICME  =	{ICME})
@String(ICASSP=	{ICASSP})
@String(ICIP  = {ICIP})
@String(ACCV  = {ACCV})
@String(ICLR  = {ICLR})
@String(IJCAI = {IJCAI})
@String(PR = {PR})
@String(AAAI = {AAAI})
@String(CVPRW= {CVPRW})
@String(CSVT = {IEEE TCSVT})
```

💡 Tip: Use \cite{} for standard citations, \citep{} for parenthetical citations, and \citet{} for inline citations.

## 📊 4. Table Formatting

LaTeX provides flexible table formatting options. Below are examples for basic tables and multi-row/multi-column tables.

Basic Table (Resizable to Page Width)

```
\begin{table*}[t]
  \centering
  \caption{Performance Comparison on Benchmark Datasets}
  \label{tab:results}
    \resizebox{\textwidth}{!}{
        \begin{tabular}{lcccc}
        \toprule[1.2pt]
        Dataset & Method & Year & Metric$_1$ & Metric$_2$ \\
        \midrule[0.4pt]
        CIFAR-10 & ExampleNet & 2024 & 85.2 & 0.92 \\
        ImageNet & AnotherNet & 2023 & 76.4 & 0.88 \\
        \bottomrule[1.2pt]
        \end{tabular}
  }
\end{table*}
```

Multi-Row & Multi-Column Table

```
\begin{table}[t]
  \centering
  \caption{Dataset Statistics}
  \label{tab:dataset_stats}
  \begin{tabular}{l|c|c}
    \hline
    \multicolumn{1}{c|}{\multirow{2}{*}{Dataset}} & \multicolumn{2}{c}{Statistics} \\
    \cline{2-3}
    & Samples & Classes \\
    \hline
    CIFAR-10 & 60,000 & 10 \\
    ImageNet & 1,280,000 & 1000 \\
    \hline
  \end{tabular}
\end{table}
```

📌 Best Practice: For visually appealing tables, reference high-quality examples from ArXiv preprints.

## 📷 5. Figure Formatting

LaTeX supports single-column and multi-column figures. Ensure your figures are high resolution (.pdf or .eps).

Single Figure

```
\begin{figure*}[t]
  \centering
  \includegraphics[width=\linewidth]{figures/example.pdf}
  \caption{Illustration of the proposed method.}
  \label{fig:method}
\end{figure*}
```

Multiple Figures (Subfigures using tabular environment)

```
\begin{figure}[t]
    \centering
    \begin{tabular}{@{}c@{\hspace{-0.25mm}}c@{}}
        \includegraphics[width=0.495\linewidth]{file 1}&
        \includegraphics[width=0.495\linewidth]{file 2}\\
        \parbox{0.495\linewidth}{\centering \footnotesize{(a) sub caption 1}} &
        \parbox{0.495\linewidth}{\centering \footnotesize{(b) sub caption 2}}
    \end{tabular}
    \caption{}
    \label{}
\end{figure}
```

📌 Best Practice: Avoid low-resolution figures; use vector graphics (.pdf) whenever possible.

## 🔧 6. Predefined Commands for Consistency

```

TODO: Latex pre-define
\def\eg{\emph{e.g}\onedot} \def\Eg{\emph{E.g}\onedot}
\def\ie{\emph{i.e}\onedot} \def\Ie{\emph{I.e}\onedot}
\def\cf{\emph{cf}\onedot} \def\Cf{\emph{Cf}\onedot}
\def\etc{\emph{etc}\onedot} \def\vs{\emph{vs}\onedot}
\def\wrt{w.r.t\onedot} \def\dof{d.o.f\onedot}
\def\iid{i.i.d\onedot} \def\wolog{w.l.o.g\onedot}
\def\etal{\emph{et al}\onedot}

\newcommand{\eg}{\emph{e.g.}}
\newcommand{\Eg}{\emph{E.g.}}
\newcommand{\ie}{\emph{i.e.}}
\newcommand{\Ie}{\emph{I.e.}}
\newcommand{\cf}{\emph{cf.}}
\newcommand{\Cf}{\emph{Cf.}}
\newcommand{\etc}{\emph{etc.}}
\newcommand{\vs}{\emph{vs.}}
\newcommand{\wrt}{w.r.t.}
\newcommand{\dof}{d.o.f.}
\newcommand{\iid}{i.i.d.}
\newcommand{\wolog}{w.l.o.g.}
\newcommand{\etal}{\emph{et al.}}

```

---

# 📚 AI Tools for Academic Writing

## 🛠️ 1. Recommended AI Tools

1. **GPT Academic** - [GitHub Repository](https://github.com/binary-husky/gpt_academic)
2. **NextChat (ChatGPT Next Web)** - [GitHub Repository](https://github.com/ChatGPTNextWeb/NextChat)

## 🎯 2. Useful Prompts

- **Bilingual Translation**

  > I want you to act as a scientific English-Chinese translator. I will provide you with a paragraph in one language, and your task is to accurately and academically translate it into the other language. Do not repeat the original text. Use natural language processing and effective writing techniques to enhance readability. Identify the original language first, then provide the translation.

- **Academic Writing Enhancement**

  > Below is a paragraph from an academic paper. Please refine it to align with formal academic style, improving spelling, grammar, clarity, conciseness, and readability. Rewrite entire sentences if necessary. First, provide the polished paragraph. Then, list all modifications in a markdown table, explaining the rationale behind each change.

- **Paper Polishing for Submission**

  > I am preparing my _[conference/journal name]_ paper for submission and require assistance in refining each paragraph for academic rigor. Please correct grammatical errors, enhance sentence structure for scholarly suitability, and formalize the tone where needed. Provide a markdown table with three columns: (1) Original sentence, (2) Highlighted revision, and (3) Explanation for the change. Finally, rewrite the fully revised paragraph. If you understand, please reply: "Yes, let's get started."

- **Persuasive Academic Writing Feedback**

  > Please review my writing style and provide feedback on how to make it more persuasive and compelling for academic submission. Include a revised version of my paragraph with enhanced readability and coherence.

- **Clarity & Readability Improvement**
  > As a non-native English speaker, I need help improving the clarity of my writing. Please check for grammar, spelling, and structural issues while suggesting clearer alternatives. Provide the fully revised paragraph.

---

# 🎨 Framework Design

## 🖥️ 1. Recommended Software

- **Microsoft PowerPoint (PPT)** – Widely used for creating high-quality visual frameworks, including oral presentation figures.
- **Visio** – Ideal for complex diagramming and flowchart creation.

## 📝 2. Font & Style Guidelines

- **Font Style**: Arial, Helvetica, Sans Serif
- **Consistent color themes** to maintain readability and professional aesthetics.

## 🎨 3. Design Resources

- **Vector Graphics Library**: [IconFont](https://www.iconfont.cn/)
- **Color Palette Generator**: [ColorKit](https://colorkit.co/)
