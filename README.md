# Portfolio Risk Concentration Analysis with Random Networks

This ongoing project investigates how mathematical network theory can be used to detect hidden risk concentrations in a financial portfolio. A key principle in portfolio construction is diversification, especially to guard against exogenous shocks. Mathematically, this is often modeled through correlations between asset returns, where lower correlations imply greater diversification.

This project extends that idea by applying concepts from network theory to uncover whether hidden risk concentrations might still exist—even in portfolios that appear diversified by traditional measures.

## Data & Network Construction:

We use Geometric Brownian Motion (GBM) to generate synthetic asset price paths, forming a toy model in the project’s current exploratory stage. A correlation matrix is computed from these returns using a sliding window, which is then converted to an Adjacency Matrix to construct a network. _These networks will be referred to as empirical networks- 

- Nodes represent assets.
* Edges are created between pairs of assets when their correlation falls within a “low correlation” range (e.g., -0.3 ≤ ρ ≤ 0.3)
  - This threshold is configurable and was chosen here for illustrative purposes.
 
## Network Analysis:

The empirical network is analysed by comparing it to well-known random network models, each of which carries different structural properties and implications:

-Erdős–Rényi (ER) Networks: Known for randomness and independence between nodes. Similarity here would suggest true diversification and no hidden clustering.
*Barabási–Albert (BA) Networks: Characterised by preferential attachment and clustering, potentially signaling dependency structures or hidden risk concentrations.

By comparing empirical network statistics—like average clustering coefficient, path length, degree distribution, and modularity—against these models, we can infer if and where dependencies exist in the portfolio structure.

## Next Steps:

-Refine network properties to analyse and establish a robust set of metrics for comparison.
*Visualise empirical vs. model statistics to identify similarities.
+Backtest using real financial data and integrate risk metrics like VaR and Sharpe Ratio.
-Quantify similarity between networks to create a meaningful alert system.

## Final Goal

To develop a risk alert mechanism that flags portfolios when their empirical network properties align closely with high-dependency models like BA—suggesting hidden concentrations of risk.
