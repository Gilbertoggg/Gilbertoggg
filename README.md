python
import time
from rdflib import Graph, Namespace, Literal
from rdflib.namespace import RDF

# Criação do grafo RDF
start_time = time.time()  # Momento inicial
g = Graph()

# Definição do namespace
ex = Namespace("http://example.org/")  # Exemplo de namespace

# Adição da declaração sobre o status de implementação do IPv6 ao grafo
g.add((ex.IPv6, ex.status, Literal("Sendo gradualmente implementado na internet")))

# Simulação do consumo das informações pelo sistema de IA
for subj, pred, obj in g:
    if subj == ex.IPv6 and pred == ex.status:
        print(f"O status de implementação do IPv6 é: {obj}")

end_time = time.time()  # Momento final
execution_time = end_time - start_time  # Tempo de execução
print(f"Tempo de execução: {execution_time} segundos")
```
