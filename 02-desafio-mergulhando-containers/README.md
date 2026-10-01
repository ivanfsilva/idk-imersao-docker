# Desafio: App Java

## Configurar o Container com Timezone GMT-3 e Restrições de Recursos

**Objetivo:**
Criar e executar um container baseado na imagem `algaworks/hello-world-java-app` com as seguintes configurações:

- **Timezone:** Configurado para GMT-3 (`America/Sao_Paulo`).
- **Porta:** A aplicação deve rodar na porta `9090` do host.
- **Limites de Recursos:**
  - **Memória:** Limitar o container a **1GB** de memória.
  - **CPU:** Limitar o container a **1 núcleo** de CPU.
  - **JVM:** Configurar a JVM para usar no máximo **70%** da memória disponível no container.

---

### Comando Docker Sugerido como resposta

```bash
docker run -d \
  --name desafio-app-java \
  -p 9090:8080 \
  --memory=1g \
  --cpus=1 \
  -e TZ=America/Sao_Paulo \
  -e JAVA_TOOL_OPTIONS="-XX:+UseContainerSupport -XX:MaxRAMPercentage=70" \
  algaworks/hello-world-java-app
```
