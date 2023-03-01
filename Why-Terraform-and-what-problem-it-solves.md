---
title: "Why Terraform and what problem is it trying to solve?"
date: 2021-08-11
author: Simon Grzebieta
draft: false
tags: ['terraform', "iac", "devops", "automation"]
---
### Why Terraform?

This is a question I've been asked many times in my career, and my answer is always: 
- It's a great tool that is easy to use. 
- It has many providers, including AWS, GCP, Azure, Kubernetes. 
- It allows you to create reusable modules. 

I was challenged on my answer recently and I wanted to elaborate on why Terraform is a good approach, so I researched the topic into why someone would choose terraform over native tools.

Firstly, to understand why you should use Terraform and what problem it is trying to solve, you need to understand what Terraform is. Terraform is an infrastructure as code (IaC) tool which allows you to provision infrastructure using DevOps practices such as version control, code review, continuous integration, automated testing and continuous deployment in a secure and safe manner. Ok, so far you’re probably thinking - well, most of the native tools can do the same, so now have a look at some of the benefits of using Terraform.

The major benefits of using Terraform are as follows:

*DevOps methodology* - Terraform can be used to follow DevOps best practices such as version control, code reviews, continuous integration, automated testing and continuous deployment in a secure and safe manner.

*Simple to use* - Terraform, in my opinion, is a very easy tool to pick up and learn. It only took me a few days to get into it, as the documentation is abundant and easy to follow, not to mention the huge online community and presence.

*Self documenting* - One benefit of using Terraform is that it almost documents itself as declaring resources/modules so that you can easily and clearly follow what has been coded.

*Cloud agnostic* - Hashicorp claims Terraform is cloud agnostic (if there is such a thing). I say this is not true as the various cloud APIs are different, thus you could not switch out an AWS resource for a GCP resource without having to rewrite the code. What they should say is that Terraform is a Multi-Cloud tool that can enable businesses to deploy to multiple cloud providers.

*Modules* - Terraform has the concept of modules meaning you can group multiple resources together to create a reusable module, which allows your code to stay dry.

*State* - When a Terraform resource is created, it creates a state for that resource that is then tracked and managed within the platform. Utilising a state file can increase the deployment time of resources. The state is usually stored in an AWS s3 bucket, GCP storage bucket, Azure blob storage and 13 other storage types.

*Workspaces* - Workspaces are a way of organising your Terraform code into logical groupings; for example splitting your network, servers and application into different state files.

*Provider Rich* - Terraform has ‘Providers’ to create resources with a third party provider via an API. Essentially, if a product has an API, a Terraform provider can be created which means it supports a large number of Providers including all of the major cloud, network, source repositories, monitoring vendors and a large number of community built providers.

So there are some of the major benefits of using Terraform but as you’d suspect there are three types of Terraform: Open Source,Cloud and Enterprise. The above benefits apply to all three and you would be right to guess the paid versions have more features. 

Terraform Cloud is the SaaS version and Terraform Enterprise is self hosted version. Let's see what additional features you get if you go with the paid versions Cloud and Enterprise.

The major benefits of using Terraform Cloud/Enterprise

### The major benefits of using Terraform Enterprise 

**Remote state management** - the state is managed for so you’ll never have to worry. 

**Remote runs** - the executions are done within enterprise so you don’t have to worry about setting up a deployment pipeline but if you do then you can still use the TFE CLI which is able to execute the run.

**Secure Variable Storage** - Terraform Cloud encrypts all variable values securely using Vault Transit backend prior to saving them. This ensures that no out-of-band party can read these values without proper authorization.

**Team management** - an access model can be enabled based on users, teams and organisations for TFE and its workspaces.

**Private module registry** - a module registry that can be shared across the organisation.

**Sentinel policy as code** - Sentinel is an embedded policy-as-code framework integrated within the HashiCorp Enterprise products and it enables fine-grained, logic-based policy decisions and can be extended to use information from external sources.
    
**Audit logging** - a dashboard is available demonstrating what infrastructure has changed and a history of runs.

**SAML for Single Sign On** - Terraform Enterprise can act as a service provider (SP) (or Relying Party) with your internal SAML identity provider (IdP).

Finally, there are two options for TFE a SaaS version or the Private Install version.

So now that we know what the major features of Terraform Enterprise are, how does it help us answer the golden question of why Terraform and what problem is it trying to solve?

I will not try to presume why others choose Terraform but I can tell you why I stand by it and it comes down to 3 main points.

- It keeps your infrastructure code dry by using modules and makes it simple to create a modular infrastructure with building blocks that can be reused by anyone within an organisation. Additionally, I can ensure that each environment can be exactly the same.

- The tool was built with a DevOps mindset in mind enabling it to be used within a DevOps environment with ease. 

- Finally what I think is a real game changer is automated governance via Sentinel policies. For example, let’s say you want to prevent all security groups from having egress and ingress set to 0.0.0.0/0. You write a policy, deploy it and any time someone tries to deploy a security group with an egress/ingress rule with 0.0.0.0/0 Terraform will stop the execution. If you can guarantee that company policies are met with an audit trail you could sit back and relax knowing no harm could be done to your environment.

### Conclusion

Terraform can truly transform how infrastructure and applications are deployed within a business. It has a clear advantage over native tools by allowing modulation of code for many different providers which can be used to create an end-to-end solution. For example, deploying a GCP GKE cluster, creating Kubernetes resources within the GKE cluster and then configuring such applications like New Relic to monitor the GKE cluster. Adding Cloud/Enterprise into the mix gives you additional security controls that give a larger enterprise peace of mind when ensuring engineers do not create security vulnerabilities when deploying infrastructure.
	
Innablr is a leading cloud engineering and next generation platform consultancy. We are hiring! Want to be an Innablr? Reach out!
