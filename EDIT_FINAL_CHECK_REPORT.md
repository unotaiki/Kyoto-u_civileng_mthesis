# 修士論文 最終確認レポート（誤字・脱字・表現・一貫性）

本レポートは、main.tex および sections/ に集約される修士論文の最終確認で指摘・修正した箇所と、修正せずに残した注意点をまとめたものである。

---

## 1. 実施した修正一覧

### 1.1 誤字・脱字

| ファイル | 修正内容 |
|----------|----------|
| **main.tex** | 「高圧縮-」→「高圧縮:」（コメント内の余分なハイフン） |
| **31_bathymetry.tex** | 「面的な地形図を作成を可能とする」→「面的な地形図の作成を可能とする」 |
| **40_prelim_SfM.tex** | 「媒質感で光が曲進」→「媒質間で光が曲進」 |
| **50_method_position.tex** | 「用いてた本研究では」→「用いた本研究では」 |
| **50_method_position.tex** | 「見かけの位置に位置に」→「見かけの位置に」（重複削除） |
| **51_method_3Dsigma.tex** | 「$\Sigma^{3D}{app}$」→「$\Sigma^{3D}_{app}$」（下付きのアンダースコア追加） |
| **52_method_color.tex** | 「$\Gamma' = n^{-2/\gamma} \Gamma$」→「$\bm{\Gamma}' = n^{-2/\gamma} \bm{\Gamma}$」（ベクトル表記の統一） |
| **52_method_color.tex** | 「散乱・吸収減衰に考慮せずとも」→「散乱・吸収減衰を考慮せずとも」 |
| **60_data_simulated.tex** | 「評価を可能となる」→「評価を可能とした」 |
| **32_photo-bathy.tex** | 「Zhanら \cite{...}水中下の」→「Zhanら\cite{...}は水中の」（助詞「は」追加、「水中下」→「水中」） |
| **70_experim_workflow.tex** | 「もしこれをこれを」→「もしこれを」（重複削除） |
| **80_eval_simulated.tex** | ラベル「\label{fig:ablation-appearance}W」→「\label{fig:ablation-appearance}」（余分な「W」削除） |
| **81_eval_field.tex** | 「幾何的精度した水底」→「幾何的に正確な水底を含めた」 |
| **81_eval_field.tex** | 「行なった」→「行った」（表記統一） |
| **99_0_appendix_apparent_depth.tex** | 「が得られる。s」→「が得られる。」（余分な「s」削除） |
| **99_1_appendix_jacobian.tex** | 「$J_{app}$」→「$J_{\mathrm{app}}$」（下付き表記の修正、2箇所） |
| **99_3_appendix_opacity_correction.tex** | 「エタンドゥ保存則」→「エタンデュ保存則」（本文52と用語統一） |
| **90_conclusion.tex** | 「LIPIS」→「LPIPS」 |

### 1.2 参照・ラベル

| ファイル | 修正内容 |
|----------|----------|
| **81_eval_field.tex** | 「\cref{chap:workflow}」→「\cref{chap:experiments}」（正しい章ラベルへ） |
| **81_eval_field.tex** | キャプション内「RS-GSには」→「RA-GSには」 |
| **81_eval_field.tex** | 「\ref{fig:eval_field_cray}」→「\cref{fig:eval_field_cray}」、「\ref{fig:eval_field_voxel_height}」→「\cref{fig:...}」 |
| **80_eval_simulated.tex** | 「\cref{s4ec:sec:opacity-correction}」→「\cref{sec:opacity-correction}」 |
| **99_2_appendix_scale_correction.tex** | 「\cref{sec:3Dsigma-correction}」→「\cref{sec:covariance-correction}」 |
| **31_bathymetry.tex** | 2つ目の図のラベル重複を解消（fig:passive-vs-active-remote-sensing → fig:ALB-principle） |

### 1.3 表現・用語の統一

| ファイル | 修正内容 |
|----------|----------|
| **70_experim_workflow.tex** | 章冒頭「本節では」→「本章では」 |
| **80_eval_simulated.tex** | チャンファー距離・F1の説明で抜けていた変数 $S_{gt}$, $S_{est}$, $\tau$ を数式で補完 |
| **80_eval_simulated.tex** | 「前手法として提案したスケール補正」→「付録で述べるスケール補正」（「前手法」を廃止） |
| **99_2_appendix_scale_correction.tex** | 「前手法であり」→「共分散補正の簡易版であり」；参照を sec:covariance-correction に変更 |
| **99_3_appendix_opacity_correction.tex** | 「前手法であり」→「簡易版であり」 |
| **30_background.tex** | 「エコトーンの例: ：」→「エコトーンの例：」（コロン重複削除） |
| **41_prelim_DR.tex** | 連鎖律の説明で「前半の $\frac{\partial \mathcal{L}}{\partial \Theta}$」→「前半の $\frac{\partial \mathcal{L}}{\partial I}$」に修正（式と一致） |
| **61_data_field.tex** | 「30$^\circ$ $sim$ 45$^\circ$」→「30$^\circ$--45$^\circ$」（sim → エンダッシュ、2箇所） |
| **81_eval_field.tex** | ボクセル表示の記述「0.08 cm単位」→「8 cm単位」（0.08 m の誤記の可能性を考慮） |

---

## 2. 修正せず残した注意点（要確認・要判断）

- **30_background.tex**  
  図キャプションで「\cite{fig:manual_river_survey}より引用」としている。reference/figure.bib に同キーがあるため現状の \cite は有効。図の出典を文献で明示する方針であればこのままでよい。

- **32_photo-bathy.tex**  
  表の脚注「※ 脚注」に対応する脚注本文がない。脚注を追加するか、該当行を削除するか検討を推奨。

- **52_method_color.tex**  
  式(49)付近で「補正後の色$\bm{c}'_k$」と「レンダリング方程式に代入すると」の間に、直前の「次式で表される補正を適用することで」と重なる説明がある。必要に応じて一文を整理すると読みやすくなる。

- **71_experim_implement.tex**  
  コードリポジトリ URL を "Splattig" → "Splatting" に修正した。実際のリポジトリ名が "Splattig" の場合は URL を戻すこと。

- **提出前**  
  main.tex の `\listoftodos[TODO]` は提出用ビルドでは無効化（todonotes の disable）されているが、\listoftodos 自体が残っているとページが出力される可能性がある。提出時は \listoftodos の行をコメントアウトすることを推奨。

---

## 3. 用語・表記の一貫性（確認済み）

- **エタンデュ**：52_method_color.tex および 99_3 で「エタンデュ」に統一済み。
- **Refractive-Aware Gaussian Splatting / RA-GS**：表記は本文で統一されている。
- **見かけの位置 / Apparent position**：初出・必要箇所で定義されており、表記は揃っている。
- **章参照**：chap:experiments（ワークフローと実装）への参照を 81_eval_field.tex で修正済み。

---

## 4. その他

- 句読点は「、。」で統一されていることを確認した。
- 数式は $...$ / \begin{equation} 等の LaTeX 形式で記述されていることを確認した。
- 専門用語の初出時の「日本語 (英語: 略称)」形式は、主要箇所で守られている。

以上を反映したうえで、必要に応じて提出用 PDF を再ビルドし、目次・相互参照・参考文献が正しく出力されているか最終確認することを推奨する。
