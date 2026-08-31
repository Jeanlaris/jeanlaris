from fastapi import FastAPI
from pydantic import BaseModel

class Sovereignty(BaseModel):
    operator: str = "Jean Laris (E1)"
    logic: str = "APEX-0 Protocol"
    status: str = "Zenith Flow 4K"
    phase: int = 2

app = FastAPI(title="Alantec Core Engine")

@app.get("/heartbeat", response_model=Sovereignty)
async def check_system():
    """
    Aciona o efeito borboleta: Mínimo esforço, Máximo impacto.
    """
    return Sovereignty()

@app.get("/health")
def health_check():
    return {"status": "operational"}
