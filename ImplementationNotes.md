# Homework

This project is at https://github.com/jeffwarnica/ansible_advance_homework

## Basic Requirements

RHC was engaged by MitziCom to provide a sample CI/CD pipeline with Ansible and Ansible tower
for provisioning a new web application.

This involved building out Ansible playbooks, and roles, to provision VMs/Instances into a QA and Production
environments (OpenStack and AWS via OpenTLC, respectively). The design indicates per-provider playbooks, 
with generic OS/Application playbooks and roles that should work in any environment

## Provision QA Environment (including smoke test)

The QA environment build entrypoint is `site-osp-instances.yml` which leverages several roles

## Provision Production Environment (including smoke test)

The Production environment build entrypoint is `aws-provisionin.yml`, in turn leveraging several custom roles.

## Design Ansible Tower Workflow Job Template

The Tower workflow, known as `cicd_workflow` leverage and exemplifies several advanced features.

The project (source code) is synced, and the workflow branches. On one branch the Production environment 
is Provisioned, and smoke tested. On the other, the QA environment is built out; the application installed, 
and smoke tested. If the QA smoke test fails, it the QA environment is destroyed. If successful, the 
application is deployed on the Production environment.

*Note*: There is no particular "wait state" in Tower workflows. The design is tha the environments are 
built in parallel, and only after QA testing would the app be deployed to Production. However, there
is nothing to prevent this from happening too soon.