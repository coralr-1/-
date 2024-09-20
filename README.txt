
# README

## 项目简介
该项目的目标是对评论数据进行清洗、情感分析，并结合作品数据进行数据分析。我们使用了 `SnowNLP` 进行情感分类，并对清洗后的评论数据进行了合并、分析和可视化。

## 文件列表

1. **cleaned_comments.csv**
   - **描述**: 这是清洗后的评论数据文件，其中包含了去除表情符号、URL、括号及其内容等无效信息的评论内容。此文件通过正则表达式清除了不必要的字符，保留了评论的核心信息。
   - **主要字段**:
     - `comment_id`: 评论的唯一标识符。
     - `content`: 清洗后的评论内容。
     - `create_time`: 评论的创建时间（时间戳格式）。
     - `user_id`: 评论用户的唯一标识。
     - `nickname`: 用户的昵称。
     - `liked_count`: 点赞数量。
     - `note_id`: 对应的作品 ID。

2. **comments.csv**
   - **描述**: 原始评论数据文件，包含用户发布的评论及相关信息。
   - **主要字段**:
     - `comment_id`: 评论的唯一标识符。
     - `content`: 原始评论内容。
     - `create_time`: 评论的创建时间。
     - `user_id`: 评论用户的唯一标识。
     - `nickname`: 用户的昵称。
     - `liked_count`: 点赞数量。
     - `note_id`: 对应的作品 ID。

3. **contents.csv**
   - **描述**: 作品数据文件，包含发布的作品以及与作品相关的统计信息。
   - **主要字段**:
     - `note_id`: 作品的唯一标识符。
     - `type`: 作品类型。
     - `liked_count`: 作品的点赞数。
     - `comment_count`: 作品的评论数。
     - `title`: 作品的标题。
     - `last_modify_ts`: 作品的最后修改时间。

4. **sentiment_analysis_results.csv**
   - **描述**: 这是在清洗后评论数据基础上生成的情感分析结果文件，包含评论的情感分类以及合并的作品数据。
   - **主要字段**:
     - `note_id`: 作品的唯一标识符。
     - `content`: 清洗后的评论内容。
     - `sentiment_class`: 根据 `SnowNLP` 进行的情感分类，分为 "positive", "neutral", "negative"。
     - `create_time`: 评论的创建时间。
     - `type`: 作品类型。
     - `liked_count`: 作品或评论的点赞数。
     - `comment_count`: 作品的评论数。

5. **snownlp.ipynb**
   - **描述**: Jupyter Notebook 文件，包含项目中用于情感分析和数据清洗的代码。该 Notebook 使用 `SnowNLP` 对评论进行情感分析，并结合了作品数据对清洗后的数据进行进一步分析。
   - **主要功能**:
     - 评论数据清洗：去除表情、URL、括号等不必要的信息。
     - 情感分析：使用 `SnowNLP` 库对评论进行情感分类。
     - 数据合并与分析：将清洗后的评论数据与作品数据合并，进行情感分类的可视化和统计分析。

## 使用步骤

1. **准备环境**:
   - 安装必要的 Python 库:
     ```bash
     pip install pandas snownlp matplotlib
     ```

2. **运行分析代码**:
   - 打开 `snownlp.ipynb`，按照 Notebook 中的步骤运行代码。此文件将会：
     - 读取 `cleaned_comments.csv` 和 `contents.csv`。
     - 对评论内容进行情感分析并合并作品数据。
     - 最后生成 `sentiment_analysis_results.csv` 供进一步分析使用。

3. **数据分析**:
   - 可以通过 Notebook 或其他工具对 `sentiment_analysis_results.csv` 进行进一步的统计分析或可视化操作，例如分析评论的情感分布、点赞数与情感的关系等。

## 参考资料
- [SnowNLP Documentation](https://github.com/isnowfy/snownlp)
