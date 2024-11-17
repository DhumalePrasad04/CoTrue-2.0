# CoTrue Analysis: Code Optimization and Carbon Emission Estimation Tool

## **Overview**

CoTrue Analysis is an interactive web-based application designed to streamline the process of code execution and optimization while also providing insights into the environmental impact of running code. Built with Streamlit, this tool offers the ability to execute Python or C code, optimize it using AI, and calculate the corresponding carbon emissions based on the selected country's electricity carbon intensity.

---

## **Features**

1. **Code Execution**: 
   - Run Python or C code directly in the app.
   - View the output or any errors generated during execution.

2. **Code Optimization**:
   - Leverages AI to suggest an optimized version of your code while maintaining its functionality.
   - Uses a conversational memory system to ensure the AI understands the context and history of interactions.

3. **Carbon Emission Estimation**:
   - Calculates carbon emissions in kilograms of CO₂ based on the runtime of your code and the carbon intensity of electricity in the selected country.

4. **Customizable User Interface**:
   - Includes a visually appealing terminal-style loader for enhanced interactivity during code execution and optimization.
   - Displays the original code, optimized code, and corresponding results in a structured and user-friendly layout.

---

## **Technologies Used**

### **Languages**
- **Python**: Primary language for building the app.
- **C**: Supported for code execution and compilation.

### **Frameworks and Libraries**
1. **Streamlit**:
   - Provides the backbone of the web application, handling UI, interactivity, and layout.
2. **LangChain**:
   - **ChatPromptTemplate**: Formats prompts sent to the AI model.
   - **ConversationBufferMemory**: Maintains context across multiple AI interactions.
3. **OllamaLLM**:
   - Handles AI-driven code optimization using the `llama3.2:1b` model.
4. **Subprocess**:
   - Executes Python or C code and captures output, errors, or runtime information.
5. **Tempfile**:
   - Creates temporary files for saving and executing user code.
6. **OS**:
   - Handles file system operations for creating and cleaning up temporary files.
7. **Time**:
   - Measures the runtime of the code for carbon emission calculation.

---

## **How It Works**

1. **Code Input**:
   - Users input their Python or C code in the text area provided.

2. **Select Language**:
   - Users select the programming language (Python or C) via a dropdown.

3. **Run Code**:
   - On clicking the "Run Code" button:
     - The code is saved temporarily and executed.
     - The output and runtime are displayed.
     - Carbon emissions are calculated using the runtime, country-specific carbon intensity, and an assumed power draw of 0.2 kWh for computation.

4. **Optimize Code**:
   - On clicking the "Optimize Code" button:
     - The code is sent to an AI model, which returns a more efficient version.
     - The optimized code is displayed alongside the original output.

5. **Loader Animation**:
   - While the code is being processed, a terminal-style loader animation is displayed to enhance user experience.

---

## **Carbon Emission Estimation**

The carbon emissions are calculated using the formula:

\[
\text{Carbon Emission (kg CO₂)} = \left( \frac{\text{Execution Time (seconds)}}{3600} \right) \times 0.2 \times \left( \frac{\text{Carbon Intensity (gCO₂/kWh)}}{1000} \right)
\]

- **Carbon Intensity Values**:
  - Carbon intensity data for different countries is stored in the app, enabling users to select their country for accurate calculations.

---

## **Setup Instructions**

### **Prerequisites**
- Python 3.9 or later
- Required Python libraries (can be installed via `requirements.txt`)

### **Installation**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/cotrue-analysis.git
   cd cotrue-analysis
   ```
2. Create a virtual environment and activate it:
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### **Run the Application**
```bash
streamlit run app.py
```

---

## **Folder Structure**

```
cotrue-analysis/
├── app.py                 # Main application script
├── requirements.txt       # Required Python libraries
├── README.md              # Project documentation
└── assets/                # Assets like screenshots or CSS files
```

---

## **Future Enhancements**

1. Support for additional programming languages (e.g., Java, JavaScript).
2. Real-time performance benchmarks for optimized code.
3. Detailed carbon footprint reports over time.
4. Integration with APIs to fetch real-time carbon intensity data.

---



## **Acknowledgments**

- **LangChain**: For providing tools to integrate language models.
- **OllamaLLM**: For the AI-driven code optimization.
- **Streamlit**: For making web application development seamless.
- **Uiverse.io**: For the terminal-style loader design.

---

With **CoTrue Analysis**, streamline your coding efficiency and make informed decisions about the environmental impact of your computational tasks. 🌱
