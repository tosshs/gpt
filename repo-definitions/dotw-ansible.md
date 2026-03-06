# Agreed Architecture

## Repository Responsibilities

- dotw-almalinux10wsl → WSL / AlmaLinux host bootstrap
- vagrant → VM lifecycle management
- dotw-ansible → infrastructure configuration (roles + playbooks)
- platformctl → main orchestration brain

## Execution Model

- platformctl calls ansible-playbook directly
- no orchestration wrappers in dotw-ansible

## dotw-ansible Structure

dotw-ansible/
  inventories/
  playbooks/
    base.yml
    k8s.yml
    okd.yml
  roles/
    common/
    k8s/
    okd/

## Scope

- configure Vagrant labs
- configure Kubernetes clusters
- configure OKD clusters
- runs from WSL control node (AlmaLinux)
cd ../

### Why This Structure

- inventories mirror Vagrant labs one-to-one
- playbooks remain thin orchestration layers
- roles stay reusable across environments
- easy to extend later for:
  - cloud labs
  - shared services
  - additional clusters

  ### Suggested dotw-ansible Structure

dotw-ansible/
  ansible.cfg
  inventories/
    vagrant/
      k8s-multinode-lab/
        hosts.yml
        group_vars/
          all.yml
          k8s_control_plane.yml
          k8s_workers.yml
      okd-lab/
        hosts.yml
        group_vars/
          all.yml
          okd_controllers.yml
          okd_computes.yml
  playbooks/
    base.yml
    k8s.yml
    okd.yml
  roles/
    base/
    k8s/
    okd/
    okd-prereqs/
    container-runtime/
  collections/
    requirements.yml
  requirements.yml
  README.md

## Targets to Configure with Ansible

- k8s-multinode-lab
  - control-plane
  - worker
  - already running

- okd-lab
  - controller
  - compute1
  - compute2
  - will exist once created

## What dotw-ansible Should Provide (Initially)

- inventory patterns for Vagrant labs (hostnames / groups)
- playbooks
  - k8s/
  - okd/
  - shared base/
- roles
  - common prerequisites
  - per-platform setup

## How platformctl Will Use It

- call ansible-playbook with the correct inventory for the chosen lab

## Open Question

Do these VMs already have SSH-reachable hostnames/IPs (from `vagrant ssh-config`)?

If yes, should the Ansible inventory be generated from that output?
