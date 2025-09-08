# Chart de helm proyecto Ikusi

Este repositorio contiene el chart de helm para poder desplegar todos los microservicios necesarios para el proyecto Ikusi.

## Requisitos

- Cluster de Kubernetes

- Helm instalado

## Instalación

Para poder instalar el chart se deben seguir los sigueintes pasos:

1. El chart se encuentra indexado en Artifact Hub en el sigueinte [enlace](https://artifacthub.io/packages/helm/ikusi-bk-chart/backend). Por lo que es neceario agregar ese repositorio a la lista local de repositorios con el sigueinte comando

```
helm repo add ikusi-bk https://kyodevcorp.github.io/ikusi-bk-chart
```

2. Actualizar los charts de los repositorios instalados

```
helm repo update
```

3. Instalar el Chart en la version deseada, en el namespace deseado.

```
helm install <release_name> ikusi-bk/backend --version <chart_tag> --namespace <namespace_to_install>
```

| Se recomienda la versión 1.0.3 por estabilidad.

## Uso de servicios

Para el uso de los servicios se tienen dos opciones las cuales estan relacionadas a los servicios de `usuarios-sercice` y `transacciones-service` las cuales son las siguientes, aplique la que mas se ajuste a su caso de uso.

1. Realizar el portfordward de ambos servicios para poder lanzar peticiones desde el host.

2. Configuracion de ingress enlazando los servicios mencionados y balanceando la carga correspondientemente.