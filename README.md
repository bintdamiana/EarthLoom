# 🌿 Earth Loom: SoCal Native Plant Explorer

**Hybrid search for 6,000+ plants in Los Angeles & Orange County**  
*Combining precise taxonomy (SQLite) with AI-powered semantic search (ChromaDB + RAG)*

➡️ **Try it**:  
```python
from earthloom import PlantFinder
finder = PlantFinder()
finder.query("Show me purple flowers near beaches")
🌟 Features
County-Filtered Data: 4,000+ LA species / 4,000+ OC species

Two Search Modes:

Exact: "Eschscholzia californica in Orange County"

Semantic: "plants that live by water sources in LA County"

RAG-Powered: Answers cite Jepson/Calflora sources

🛠️ Setup
Install:

bash
git clone https://github.com/bintdamina/earthloom.git
cd earthloom
pip install -r requirements.txt  # sqlite3, chromadb, sentence-transformers
Initialize Databases (run once):

bash
python build.py --counties "Los Angeles,Orange"
📂 Data Structure
python
# Each plant record contains:
{
  "scientific_name": "Malosma laurina",
  "common_name": "Laurel sumac", 
  "counties": ["Los Angeles"],  # LA and/or Orange only
  "chroma_id": "malosma_laurina_la"  # Vector reference
}
🌱 Example Queries
Type	Command	Best For
Taxonomic	finder.query(scientific="Quercus agrifolia")	Botanists
Location	finder.query(county="Orange", bloom_season="spring")	Hikers
AI Hybrid	finder.query("dog safe plants near parks")	Gardeners
🚧 Coming Soon
Plant descriptions for richer RAG responses

Mojave Desert and San Diego County expansion

Spanish language support

💡 Pro Tip: Use finder.debug = True to see search logic!
🐛 Found an issue? Open a ticket by emailing:

earthloom@gmail.com

---

### Why This Works:
1. **Accurate Scope**: Clearly states LA/OC focus and Phase 1 fields
2. **RAG Visibility**: Shows AI capabilities without overpromising
3. **Copy-Paste Friendly**: Clean formatting, no placeholder text
4. **Actionable Examples**: Ready to run query types for different users

**To add later** (when Phase 2 is ready):  
```markdown
## 📚 RAG Context Expansion
New in v0.2: Plant descriptions enable queries like:
```python
finder.query("Fuzzy green leaf with yellow flowers growing by the LA River")
finder.query("Explain why coast live oaks resist wildfires")
