### Objetivos
- Praticar deploy Canary 
  - Canary de usuário final
  - Canary Focado
- Inicialmente voltado para minikube, ao final voltado para cloud.
- A configuração Inicialmente será com ingress-nginx
### Aplicação usada como base:
[Veja esse projeto](https://github.com/Adenilson365/devopslabs01-serviceMesh), será reutilizado toda a configuração de aplicação, e todo o ambiente até a configuração do Istio. Seguirei desse passo.
- **O que esperar**, nesse repositório apenas _**rollout canary**_ usando _**Istio**_.

## Configurar o NGINX
- Para usar local, adicione uma linha no seu arquivo de hosts:
```
    <ip_onde_esta_rodando_frontend> <dominioLocal>
    exemplo:
    192.168.49.2 api-local.com
    192.168.49.2 dev.api-local.com
```
- Também pode usar o [nip.io](https://nip.io/), assim não precisará editar seu arquivo hosts

### No Ingress precisa ter a annotation abaixo:
```
    nginx.ingress.kubernetes.io/service-upstream: "true"
```
- Dessa forma o nginx vai conseguir direcionar tráfego através do virtualService do Istio.


