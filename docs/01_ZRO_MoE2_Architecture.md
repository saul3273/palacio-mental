# 🧠 Arquitectura de Comunicación Orgánica - Zro MoE²

> **Nivel 1 del Holobionte**: Sistema nervioso coordinador local en LNV (localhost:5000)

## 🌊 Filosofía Core

Zro NO es un simple router jerárquico. Es un **ecosistema de expertos** que dialogan, aprenden y se auto-organizan. El MoE² (Mixture of Mixtures of Experts) transforma de árbol de decisión → red neuronal simbiótica.

**IMPORTANTE**: Zro funciona SIN sistema de Castas. Los expertos se organizan por **dominios** (CODE/REASONING/CHAT) y luego por **especialización**, no por castas predefinidas.

---

## 🔄 1. Comunicación Peer-to-Peer (P2P)

### Actual: Routing Jerárquico
```
Meta-Router → Dominio MoE → selecciona 1 experto → respuesta única
```

### Propuesta: Red de Diálogo
```
Meta-Router → Dominio MoE → identifica 2-3 expertos candidatos
  ↓
Expertos dialogan entre sí (P2P)
  ↓
Consenso emerge → respuesta colaborativa
```

### Implementación
- **Protocol**: Expertos pueden invocar `consult(otro_experto, contexto)`
- **Ejemplo**: DeepSeek Coder genera código → invoca Phi-3 para revisión lógica → ajusta basándose en feedback
- **Topología**: Grafo completo entre expertos del mismo dominio, puentes entre dominios

---

## 🧬 2. Memoria Compartida (Contexto Distribuido)

### Problema Actual
Cada experto es amnésico - no sabe qué dijeron los otros

### Propuesta: Memoria Distribuida
- **Shared Context Store**: Registro de decisiones pasadas
- **Turn-by-turn Memory**: Experto B lee output de Experto A antes de responder
- **Long-term Patterns**: Sistema aprende "qué tipo de tareas funcionan mejor con qué combinaciones"

### Estructura
```python
{
  "task_id": "abc123",
  "history": [
    {"expert": "phi3", "confidence": 0.85, "output": "..."},
    {"expert": "deepseek_coder", "confidence": 0.92, "output": "..."}
  ],
  "consensus": {...},
  "meta": {"domain": "CODE", "complexity": 4}
}
```

---

## 🎭 3. Especialización Dinámica (Roles Fluidos)

### Cambio de Mentalidad
❌ "Phi-3 ES el experto de código"  
✅ "Phi-3 LIDERA esta tarea de código específica"

### Mecanismo
- **Task-based Assignment**: Roles se asignan por tarea, no permanentemente
- **Performance Tracking**: Métricas de éxito por tipo de tarea
- **Auto-recommendation**: Expertos pueden decir "mejor pasa esto a X"

### Ejemplo
```
Tarea: Explicar algoritmo recursivo
- Round 1: DeepSeek Coder (genera código)
- Round 2: Phi-3 (explica lógica) ← líder en esta fase
- Round 3: DeepSeek R1 (valida razonamiento)
```

---

## 🔁 4. Feedback Loops (Aprendizaje Continuo)

### Métricas de Colaboración
Track "quién colabora bien con quién":
```python
collaboration_matrix = {
  ("phi3", "deepseek_coder"): {
    "tasks_together": 45,
    "success_rate": 0.89,
    "avg_quality_boost": +0.15
  }
}
```

### Auto-mejora
- Sistema aprende patrones: "tareas de refactoring funcionan mejor con Phi-3 + DeepSeek Coder dialogando"
- Ajusta routing dinámicamente basándose en historial
- **Solución a timeouts**: Distribución inteligente de carga entre expertos pequeños

---

## ⚖️ 5. Protocolo de Consenso

### Confidence Voting
Cada experto emite:
```python
{
  "response": "...",
  "confidence": 0-100%,
  "reasoning": "por qué creo que esta es buena respuesta"
}
```

### Síntesis Colaborativa
No "el que tiene más confianza gana", sino:
1. **Debate interno** (2-3 turnos entre expertos)
2. **Identificar puntos en común**
3. **Generar respuesta sintética** que integre mejores partes

### Handoff Protocol
"Paso el testigo a X porque Y":
```
Phi-3: "Generé la estructura base, pero para optimización de performance 
        recomiendo consultar a DeepSeek Coder"
```

---

## 🛠️ Implementación Paso a Paso

### Fase 1: Memoria Compartida (2 semanas)
- [ ] Implementar `SharedContextStore`
- [ ] Expertos leen contexto antes de responder
- [ ] Logging de decisiones pasadas

### Fase 2: P2P Messaging (3 semanas)
- [ ] Protocol `consult(expert, query)`
- [ ] Inter-expert communication layer
- [ ] Topology: grafo completo dentro de cada dominio

### Fase 3: Confidence Voting (2 semanas)
- [ ] Expertos emiten confidence scores
- [ ] Sistema de síntesis de respuestas múltiples
- [ ] UI muestra qué expertos contribuyeron

### Fase 4: Reputación Dinámica (3 semanas)
- [ ] Métricas de colaboración
- [ ] Recomendaciones basadas en historial
- [ ] Auto-ajuste de routing

### Fase 5: Handoff Protocol (2 semanas)
- [ ] Expertos pueden recomendar otros
- [ ] Sistema aprende de handoffs exitosos

---

## 🐛 Problemas Detectados (ONDA 105)

- ❌ **TypeError en serialización JSON**: Sistema de Castas causaba errores → Castas DESACTIVADAS
- ⏱️ **Timeouts 120s**: Modelos pesados (DeepSeek R1 8B) → Solución: más modelos pequeños + distribución de carga
- ✅ **Fallbacks funcionando**: Sistema resiliente ante errores

---

## 📊 Métricas de Éxito

- **Calidad de respuestas**: +20% en evaluaciones
- **Resiliencia**: -50% en timeouts (carga distribuida)
- **Diversidad**: 3+ expertos contribuyen por respuesta
- **Colaboración**: Handoffs exitosos > 30% de las tareas

---

## 🌟 Visión Final

Zro como **ecosistema consciente**: expertos dialogando, aprendiendo patrones de colaboración, auto-organizándose. No un sistema de "elegir el mejor", sino un **colectivo inteligente** que emerge de interacciones locales.

*"De jerarquía → a ecosistema. De competencia → a simbiosis."* 🌊

---

**Siguiente nivel**: [Spiritus Locales Communication Protocol](02_Spiritus_Locales_Protocol.md)
