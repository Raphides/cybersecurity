# Openshift SDN

## Egress Router

No caso de vários nós tendo que acessar um aplicativo protegido por firewall, temos um problema. Qual a solução? Permitir que todos os IPs diferentes dos nós acessem?

Para isso, há o egress router.


### Node Selector
Para caso com muitos nós, não é ideal permitir tantos IPs. Por isso, utiliza-se o Node Selector. Nele, escolhemos só poucos nós específicos para terem seus IPs liberados pelo firewall. Qualquer tarefa que necessite de comunicação com recursos protegidos por firewall precisa ter envolvimento dos nós com IPs liberados.

### Taint


## Kubernetes CNI e Openshift Network Plugins

![](https://meatybytes.io/posts/openshift/ocp-features/overview/core-foundations/networking/cni/ocp-cni-updated_huf2d02d3a34e59430e8601b93da3ac834_199896_660x0_resize_box_3.png)

## Network Policies
