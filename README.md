# LeetStat 📊

A Jupyter Notebook-based tool to fetch, analyze, and visualize your LeetCode submission statistics and performance metrics.

## Overview

**LeetStat** helps you track your LeetCode progress by retrieving your submission data through the LeetCode GraphQL API and presenting comprehensive statistics including:

- Overall problem-solving metrics by difficulty level
- Year-to-date problem completion tracking
- Monthly productivity trends and growth rates
- Day-of-week solving patterns
- Weekly velocity calculations

## Features

### 1. **User Statistics Dashboard**
   - Fetch your overall LeetCode stats (Easy, Medium, Hard problems solved)
   - View total submissions vs. accepted submissions
   - Quick overview of your progress at a glance

### 2. **Submission History Analysis**
   - Retrieve full submission history from your LeetCode account
   - Filter for distinct new problems solved in a specific year (currently 2026)
   - Track first accepted submission date for each problem

### 3. **Performance Insights**
   - **Monthly Velocity**: See how many distinct problems you solved each month
   - **Growth Rate**: Calculate month-over-month growth percentage
   - **Day of Week Distribution**: Identify which days you're most productive
   - **Weekly Velocity**: Average problems solved per week across your solving period

### 4. **Interactive DataFrames**
   - View data in formatted pandas DataFrames
   - Built for Google Colab with rich HTML display support
   - Easy-to-read tables and statistics

## Requirements

- Python 3.x
- `requests` - for API calls
- `pandas` - for data manipulation
- `tqdm` - for progress tracking
- `IPython` - for display formatting
- Google Colab (or Jupyter Notebook with similar IPython support)

## Setup & Usage

### Prerequisites

1. **LeetCode Username**: Your public LeetCode username
2. **LeetCode Session Cookies** (for authenticated requests):
   - `LEETCODE_SESSION` cookie
   - `csrftoken` cookie
   - These are required for accessing private submission history

### Getting Your Cookies

1. Log in to [LeetCode.com](https://leetcode.com)
2. Open Developer Tools (F12) → Application → Cookies
3. Copy the values of `LEETCODE_SESSION` and `csrftoken`

### Running the Notebook

1. Open the notebook in Google Colab or Jupyter
2. **Cell 1**: Enter your LeetCode username when prompted
3. **Cell 2**: Add your session cookies and run to fetch full submission history
4. **Cell 3 & 4**: Run to generate insights and statistics

## Notebook Sections

### Cell 1: Basic User Statistics
Fetches your overall LeetCode performance metrics without authentication.

```python
# Input: Your LeetCode username
# Output: DataFrame with problems solved by difficulty
```

### Cell 2: Full Submission History
Retrieves your complete submission history (requires authentication).

```python
# Input: LEETCODE_SESSION and CSRF_TOKEN
# Output: 969+ total submissions analyzed
```

### Cell 3: Monthly Statistics
Breaks down problem-solving by month with growth rates.

```python
# Output Example:
# February: 16 problems
# March: 38 problems (+137.50%)
# April: 37 problems (-2.63%)
```

### Cell 4: Advanced Insights
Generates comprehensive insights including day-of-week patterns and weekly velocity.

## Output Example

```
--- Key Insights for 2026 ---

1. Most Productive Month: March (38 solves)

2. Monthly Velocity & Growth:
   February: 16 problems
   March: 38 problems (↑137.50%)
   April: 37 problems (↓-2.63%)

3. Day of the Week Distribution:
   Monday: 15, Tuesday: 18, Wednesday: 14, ...

4. Consistency Check: You are averaging approx 4.2 new problems per week.
```

## Sample Statistics

The notebook successfully analyzed **969 total submissions** and identified **91 distinct new problems solved in 2026**:

- **Easy**: 159 problems solved
- **Medium**: 166 problems solved  
- **Hard**: 20 problems solved
- **Total**: 345 problems solved (all-time)

## API Reference

### Endpoints Used

- **LeetCode GraphQL**: `https://leetcode.com/graphql/`

### Queries

1. **getUserStats**: Retrieves aggregated stats by difficulty
2. **submissionList**: Fetches paginated submission history (20 items per page)

## Important Notes

⚠️ **Authentication**: The full submission history requires valid LeetCode session cookies. Public stats are available without authentication.

⚠️ **Rate Limiting**: The notebook includes a 0.5s delay between API calls to respect rate limits.

⚠️ **Session Expiry**: Your LeetCode session cookies may expire. If you encounter errors, refresh your cookies.

## Data Privacy

- This tool only reads your publicly available LeetCode data
- Session cookies are stored locally in your Colab/Jupyter environment
- No data is sent to external servers beyond LeetCode's official API

## Future Enhancements

- [ ] Visualizations (charts/graphs) for better insights
- [ ] Export statistics to CSV/JSON
- [ ] Problem category breakdown (Array, String, Tree, etc.)
- [ ] Language-wise solution breakdown
- [ ] Difficulty progression analysis
- [ ] Comparison with global LeetCode statistics

## Troubleshooting

### Error: "Could not find user"
- Check that your LeetCode username is correct
- Username is case-sensitive

### Error: "Failed to fetch data. Status Code: 401/403"
- Your session cookies have expired
- Update your `LEETCODE_SESSION` and `csrftoken` values

### Error: "Could not retrieve submission list"
- Verify your cookies are correctly formatted
- Ensure you have sufficient permissions on your LeetCode account

## License

MIT License - Feel free to use and modify for personal use.

## Contributing

Feel free to suggest improvements or report issues!

## Resources

- [LeetCode](https://leetcode.com)
- [LeetCode API Documentation](https://leetcode.com/graphql)
- [Pandas Documentation](https://pandas.pydata.org/docs/)

---

**Happy Coding! 🚀**
