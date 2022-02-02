# IP Addresses

Quando si utilizza openshift-installer in ambiente vSphere richiede due IP addresses statici, vengono forniti infase di installazione tramite script:

* **API** - usato per accedere alle cluster API.
* **Ingress** - usato per il traffico in ingresso alle applicazioni.

A virtual IP address for each of these should be specified in the [install configuration](install.md#create-configuration).

# DNS Records

I record DNS devono essere propriamente definiti.
The records should have the following values:

| Name                                  | Value       | esempio        |
| -                                     |  -          |  -             |
| `api.<cluster-name>.<base-domain>`    | API VIP     | 192.168.1.24   |
| `*.apps.<cluster-name>.<base-domain>` | Ingress VIP | 192.168.1.25   |

Note that `cluster-name` and `base-domain` are variables custom to an installation and
must correspond to the values specified in the [install configuration](install.md#create-configuration).