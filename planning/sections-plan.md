## Chapter 1: Introduction (序論)
### 1.1 Background & Motivation: 水域環境モニタリングの重要性と、UAV写真測量の台頭。

### 1.2 Problem Statement: 気水界面における「光の屈折」による幾何学的破綻。従来手法（MVS）および既存のNeural Rendering手法の限界。

### 1.3 Objectives: 物理的に正確な屈折モデルと3DGSの統合による、幾何学的精度と光学的写実性の両立。

### 1.4 Thesis Outline: 本論文の構成。

## Chapter 2: Literature Review (既往研究の概観)
【ここがご質問のMVS/NeRFを議論する重要な章です】

### 2.1 Principles of Photogrammetry & MVS:

共線性条件（Collinearity Condition）の基礎。

SfM (Structure from Motion) と MVS (Multi-View Stereo) のパイプライン。

水中（Two-media）写真測量における従来の補正アプローチ（反復計算等）とその限界。

### 2.2 Neural Radiance Fields (NeRF) and Volumetric Rendering:

Implicit Representation（陰的表現）の革命。

NeRFの基礎原理と、水中シーンへの応用例（SeaThru-NeRF等）。

NeRFの課題：学習・推論速度、幾何形状抽出（Mesh化）の難しさ、ブラックボックス性。

### 2.3 3D Gaussian Splatting (3DGS):

Explicit Representation（点群ベース）への回帰とRasterizationによる高速化。

なぜMVSでもNeRFでもなく、本研究で3DGSを選択するのか（幾何制御性とレンダリング品質のバランス）。

## Chapter 3: Theoretical Formulation of Refractive Geometry (屈折幾何学の理論的定式化)
【Full Paperには書ききれなかった数理的な詳細を記述する章です】

### 3.1 The Two-Media Imaging Model: 空気-水界面の物理モデル。Snellの法則のベクトル解析的記述。

### 3.2 Analytical Refraction Mapping:

水中点（Object space）からカメラ（Image space）への光線追跡の定式化。

見かけの深度（Apparent depth）と真の深度（True depth）の関係性。

### 3.3 Differentiable Transformation:

逆伝播（Backpropagation）のための勾配計算。

Jacobian Matrixの導出（ここを詳細に！）。屈折がガウス分布の形状（共分散行列）に与える影響の数理的解析。

## Chapter 4: Proposed Method: Refraction-Aware 3DGS (提案手法)
【実装レベルのシステム構成を記述する章です】

### 4.1 Framework Overview: システム全体のパイプライン。

### 4.2 Adaptation of 3D Gaussians for Water:

屈折を考慮したSplattingアルゴリズムの実装。

水中減衰（Absorption/Scattering）の考慮（もし行っていれば）。

### 4.3 Optimization Strategy:

Loss Functionの設計（Photometric loss, Geometric constraints）。

Densification（ガウス分布の増殖）とPruning（削除）の制御戦略。

Chapter 5: Experiments and Evaluation (実験と評価)
### 5.1 Dataset Generation:

物理ベースレンダラ（Blender/Cycles等）を用いたシミュレーション環境の構築。

Ground Truth（真値）の定義。

### 5.2 Implementation Details: ハイパーパラメータ、計算環境。

### 5.3 Comparative Analysis:

vs. Colmap (Traditional MVS w/o refraction correction)

vs. NeRF-based methods (e.g., Instant-NGP adaptation)

vs. Standard 3DGS

定量的評価 (PSNR, SSIM, LPIPS, Geometric Error/F1-score)

定性的評価 (Visual quality, Point cloud density)

### 5.4 Ablation Studies: 提案した屈折モジュール有無による効果検証。

## Chapter 6: Discussion (考察)
### 6.1 Analysis of Geometric Fidelity: なぜ提案手法が幾何学的に正しい結果を出せたのか、理論と結果の突き合わせ。

### 6.2 Limitations:

動的な水面（波）への対応限界。

極度の濁りや照明条件への依存性。

計算コストの分析。

### 6.3 Future Directions: 動的シーンへの拡張、実海域への適用ロードマップ。

## Chapter 7: Conclusion (結論)
### 7.1 Summary of Contributions:

### 7.2 Final Remarks: