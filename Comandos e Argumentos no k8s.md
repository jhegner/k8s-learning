# Comandos e Argumentos no Kubernetes

Assim como no Docker é possivel passar comandos e argumentos no K8s para a imagem

## Dockerfile

FROM ubuntu

ENTRYPOINT ["sleep"]

CMD ["5"]

## pod-definition.yaml

<pre><code>
apiVersion: v1
kind: Pod
metadata:
  name: ubuntu-sleeper-pod
spec:
  containers:
    - name: ubuntu-sleeper
      image: ubuntu-sleeper
      command: ["sleep2.0"] # substitui o comando no ENTRYPOINT
      args: ["10"] # valor do argumento a ser passado para o container ao ser iniciado
</code></pre>
