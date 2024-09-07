# How to quantifying search relevance

Whether it's a global search giant like Google or a specialized e-commerce platform, the effectiveness of a search engine hinges on one key metric: **search relevance**. But what exactly is search relevance, and how can it be quantified? I have tried to pen down a few of the learnings from the experience of working as a Search Engineer at [Blibli.com](https://blibli.com).
Before we dive deeper into how to measure search relevance, let’s briefly know what search relevance is.

## What is Search Relevance?

Search relevance refers to how well the search results match a user’s query. It’s the measure of how closely the results returned by a search engine align with the user's intent. A relevant search result should not only match the keywords entered by the user but also satisfy the underlying intent behind the query.

For example, a search for "best smartphones 2024" should ideally return a list of the latest smartphones, along with reviews, comparisons, and recommendations.

## Why is Search Relevance Important?

Search relevance is critical because it directly impacts user satisfaction and engagement. If a search engine consistently returns irrelevant results, users are likely to abandon the platform, leading to decreased user retention and lower revenue, especially in e-commerce scenarios.

## But, is it even possible to measure search relevance?
Relevance is a subjective topic and it is more like Monalisa's painting, as in it depends on who the audience is. But giving a short answer, Yes. 
We do it all the time. Sound's weird right? Yes I know.


So we measure or we better to say, we try to measure the relevance based on **"Data points"**.

## Quantifying Search Relevance: Key Metrics

To quantify search relevance, we rely on a variety of metrics. These metrics can be broadly categorized into two types: **offline metrics** and **online metrics**.

### Offline Metrics

- **Precision**: Precision is the ratio of relevant documents retrieved to the total number of documents retrieved. It answers the question: "Of all the results shown, how many were actually relevant?"

  \[
  \text{Precision} = \frac{\text{Number of Relevant Results Retrieved}}{\text{Total Number of Results Retrieved}}
  \]

- **Recall**: Recall is the ratio of relevant documents retrieved to the total number of relevant documents available. It answers the question: "Of all the relevant results, how many did the search engine retrieve?"

  \[
  \text{Recall} = \frac{\text{Number of Relevant Results Retrieved}}{\text{Total Number of Relevant Results Available}}
  \]

- **F1 Score**: The F1 score is the harmonic mean of precision and recall, providing a single metric that balances both. It’s particularly useful when you need to weigh precision and recall equally.

  \[
  \text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}
  \]

- **Mean Reciprocal Rank (MRR)**: MRR is the average of the reciprocal ranks of results for a sample of queries. It measures the rank at which the first relevant document appears.

  \[
  \text{MRR} = \frac{1}{|Q|} \sum_{i=1}^{|Q|} \frac{1}{\text{rank}_i}
  \]
  where \( \text{rank}_i \) is the rank of the first relevant document for query \(i\), and \( |Q| \) is the number of queries.

- **Normalized Discounted Cumulative Gain (nDCG)**: nDCG is a metric that considers both the relevance and the position of search results. It provides a score between 0 and 1, where a higher score indicates better relevance and ranking.

  \[
  \text{DCG} = \sum_{i=1}^{n} \frac{2^{\text{rel}_i} - 1}{\log_2(i + 1)}
  \]
  \[
  \text{nDCG} = \frac{\text{DCG}}{\text{IDCG}}
  \]
  where \( \text{rel}_i \) is the relevance score of the result at position \(i\), and \( \text{IDCG} \) is the ideal DCG, representing the best possible ordering of results.

### Online Metrics

- **Click-Through Rate (CTR)**: CTR measures the ratio of users who click on a search result to the total number of users who viewed the search result. A higher CTR often indicates higher relevance.

  \[
  \text{CTR} = \frac{\text{Number of Clicks}}{\text{Number of Impressions}}
  \]

- **Dwell Time**: Dwell time is the amount of time a user spends on a page after clicking a search result. Longer dwell times suggest that the result was relevant and engaging.

- **Bounce Rate**: Bounce rate measures the percentage of users who return to the search results page without interacting with the content on the clicked result. A high bounce rate may indicate irrelevant or low-quality results.

- **Conversion Rate**: For e-commerce and transactional queries, the conversion rate—whether a user completes a purchase, signs up for a service, etc.—is a critical indicator of search relevance.

## Practical Considerations

1. **Dataset Selection**: Choose a representative set of queries and ground truth data for evaluating search relevance. The dataset should cover various query types and user intents.

2. **User Feedback Loop**: Incorporate user feedback into your relevance evaluation process. Tools like A/B testing can help measure the impact of changes to your search algorithm in real-time.

3. **Balancing Precision and Recall**: Striking the right balance between precision and recall is crucial. Depending on the context, you might prioritize one over the other. For instance, in medical or legal search engines, recall might be more important than precision.

4. **Handling Long-Tail Queries**: Long-tail queries, which are less frequent but highly specific, pose a unique challenge. Ensure that your relevance metrics are robust enough to handle these queries.

## Conclusion

Quantifying search relevance is a complex but essential task. By leveraging the right mix of offline and online metrics, you can gain valuable insights into how well your search engine is performing and identify areas for improvement. Whether you're optimizing an e-commerce search engine or a large-scale web search platform, these methodologies will help you deliver more relevant and satisfying search experiences to your users.

## Further Reading

- "Introduction to Information Retrieval" by Christopher D. Manning, Prabhakar Raghavan, and Hinrich Schütze
- "Modern Information Retrieval" by Ricardo Baeza-Yates and Berthier Ribeiro-Neto
- Google's Research Papers on Search Evaluation Metrics