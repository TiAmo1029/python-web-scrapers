# Python 网络爬虫项目合集

本项目是我为实践和展示数据采集与处理能力而开发的网络爬虫合集。每个脚本都针对不同类型的网站和反爬策略，运用了不同的技术方案。

## 🚀 项目列表

### 1. 豆瓣读书Top 250爬虫 (`douban_scraper.py`)

*   **目标站点:** 豆瓣读书Top 250榜单，一个经典的**静态渲染**网站。
*   **技术栈:** `requests`, `parsel`, `pandas`
*   **核心实现:**
    *   通过编程方式动态生成URL，实现了**多页翻页爬取**。
    *   利用 `parsel` 库强大的 **CSS选择器**，对HTML进行解析，精准提取书名、作者、评分、简介等结构化数据。
    *   对提取的原始文本，综合运用了字符串方法和**正则表达式**进行深度清洗，解决了作者信息混杂等“脏数据”问题。
    *   最终通过 **Pandas** 将所有清洗后的数据，统一输出为格式规范的CSV文件。

### 2. 58同城房源信息爬虫 (`58_scraper.py`)

*   **目标站点:** 58同城房源列表，一个使用 **AJAX技术动态加载**数据的现代网站。
*   **技术栈:** `requests`, `pandas`, `json`
*   **核心实现:**
    *   **采用“API直连”策略:** 摒弃了低效复杂的HTML解析，通过在浏览器开发者工具中分析**XHR**网络请求，直接定位并模拟调用了网站背后加载数据的**后端API接口**。
    *   **极高的爬取效率:** 该方法直接获取结构化的**JSON数据**，完全绕过了前端复杂的HTML结构和潜在的反爬脚本，**数据获取效率相比传统解析方式提升了10倍以上**。
    *   **强大的鲁棒性:** 直接处理JSON数据，使得数据提取逻辑极其稳定，不受前端页面样式改版的影响，极大地提升了爬虫的**可维护性**。

### 🔧 如何在本地运行

1.  **克隆本仓库:**
    ```bash
    git clone https://github.com/TiAmo1029/python-web-scrapers.git
    cd python-web-scrapers
    ```

2.  **创建并激活Python虚拟环境:**
    ```bash
    python -m venv venv
    # Windows系统:
    venv\Scripts\activate
    # macOS / Linux系统:
    # source venv/bin/activate
    ```

3.  **安装所需依赖:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **运行指定的爬虫脚本:**
    ```bash
    python douban_scraper.py
    ```# python-web-scrapers
