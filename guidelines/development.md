# Guidelines for development

Contents:

- Clean code
- Ansible Roles
- Helm

## Clean code

Write code conform the [Clean Code book](http://cleancoder.com/products).

## Ansible

Ansible is used to install the various platform components.

### Ansible roles

Ansible roles are repeatable and idempotent.

### Ansible variables

Local variables in an Ansible role, start with the name of that Role.

For example:
```
 gitlab.a_local_variable
```

### Ansible environment

Environment specific configuration is maintained in a separate configuration file, to allow for role-deployment in various infrastructures.

### Ansible default environment

Environment specific configuration defaults to the local environment.

For example:
```
{{ minikube.local_var | default('foo') }}
```

### Ansible modules

Ansible modules are wherever possible used to perform tasks, to increase readability and maintainability.

For example - public module for Kubectl:

```
# Using the Ansible k8s module, ref. https://docs.ansible.com/ansible/latest/collections/community/kubernetes/k8s_module.html
- name: Create a k8s namespace named "test"
  community.kubernetes.k8s:
    kind: Namespace
    name: test
    api_version: v1
    state: present
```

For example - private module for Helm, embedded in CNO [platformer-runner](https://gitlab.com/logius/cloud-native-overheid/components/platform-runner/-/blob/main/playbook/modules/helm3.py):

```
helm3:
    chart: nginx
    repo: https://kubernetes-charts.storage.googleapis.com/
    release: nginx
    version: 1.2.3
    namespace: nginx-ingress
    state: present
```
### Ansible file management

- Use `{{ role_path }}` for pointing to files in a role
- Use `lookup('file', ...)` to read from the role's files folder
- Use `lookup('template', ...)` to read from the role's templates folder

## Helm

Helm is used within Ansible to install the various platform components.

### Helm repositories

External repo's are used to avoid unavailable or outdated local chart repositories

### Helm release names

Releasename is named the same as the chartname.
