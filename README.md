# Recipe-Creator-Agent
Create a virtual environment

Open the Terminal and create a python virtual environment.



1) Windows
python3 -m venv aienv
aienv/scripts/activate

2)Install required libraries

pip install phidata openai duckdb exa_py pypdf packaging
pip install sqlalchemy pgvector
pip install -U "psycopg[binary]"

3)Set environment variables

export OPENAI_API_KEY=****
export EXA_API_KEY=****


4 )  Run PgVector using Docker


docker run -d \
-e POSTGRES_DB=ai \
-e POSTGRES_USER=ai \
-e POSTGRES_PASSWORD=ai \
-e PGDATA=/var/lib/postgresql/data/pgdata \
-v pgvolume:/var/lib/postgresql/data \
-p 5532:5432 \
--name pgvector \
phidata/pgvector:16


5)  Run the agent
python ai_recipe_creator_agent.py


