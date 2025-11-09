# CLARITY-AI

An interactive single-page application (SPA) that translates social media slang into formal English. This project is a web-based, interactive deployment of a data analysis report, bringing the original notebook's findings and its final "model" to life.

The application allows users to not only use the translator in real-time but also to explore the data analysis, visualize key insights, and understand the data science workflow that made it possible.

---
🚀 Features
This application is organized into five main sections, accessible via a tabbed navigation menu:

Live Normalizer: A real-time, side-by-side translator. Type any text containing slang in the input box, and the normalized, formal output appears instantly.

Data Exploration: Summarizes the data cleaning process from the original analysis. It shows key stats, such as the initial row count (1548), duplicates removed (102), and the final dictionary size (1446), as well as a sample of the cleaned data.

Analysis & Insights: Presents interactive visualizations (powered by Chart.js) for the key findings from the original report:

Distribution of Slang Length: A bar chart (histogram) visually confirming the data's heavy right-skew (skewness: 1.56).

Slang vs. Meaning Length: A scatter plot illustrating the moderate positive correlation (r = 0.476) between the length of a slang term and its meaning.

Add Slang: A form that allows you to dynamically add new slang words and their meanings to the application's dictionary. (Note: These additions only last for your current browser session).

About the Process: A detailed breakdown of the 5-step data science workflow used in the original project:

Data Ingestion

Cleaning & Processing

"Model" Building (Dictionary)

"Prediction" Function

Deployment (this web app)
---
💻 Tech Stack
This project is built with a focus on simplicity and accessibility, using no build tools or complex frameworks. All resources are loaded via CDN.

HTML5: For the core structure and content.

Tailwind CSS: For all styling, loaded via the Tailwind CDN.

Chart.js: For the interactive bar and scatter charts, loaded via CDN.

Vanilla JavaScript (ES6+): For all application logic, including:

Tabbed navigation

Real-time text normalization

Chart.js rendering

Dynamic addition of new slang

🛠️ How It Works
The "model" from the original data analysis notebook is implemented here as a simple JavaScript object (slangData) which acts as a high-speed lookup table (a hash map).

A user types in the #slangInput text area.

An onkeyup event listener fires, capturing the new text.

The normalizeSlang() function is called. This function:

Splits the input sentence into an array of words.

For each word, it cleans it by converting it to lowercase and stripping all punctuation.

It then attempts to find the cleanWord as a key in the slangData object.

If a key is found, its value (the meaning) is returned.

If no key is found, the original word is returned.

The resulting array of words is joined back into a string and displayed in the #normalizedOutput div.

Note: The slang dictionary (slangData) and chart data (histData, scatterData) in the .html file are hardcoded. The dictionary is a representative subset of the full 1446 entries from the original analysis.
