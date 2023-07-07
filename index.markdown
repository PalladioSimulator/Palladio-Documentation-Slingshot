---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<img src="images/logo.png" alt="slingshot-logo" width="150"/>
# Engineering Elasticity Policies <br> for Cloud-native Applications <br>with Slingshot

This page provides a documentation of the Slingshot approach for engineering elasticity policies for cloud-native applications. The approach is based on the following components:

The approach builds upon the Palladio approach (<a href='https://www.palladio-simulator.com'>palladio-simulator.com</a>) and contributes the following components:
 
* The *Scaling Policy Definition (SPD)* language to model your scaling policies at the architectural-level. 
<br><a href="spd">[⇢ The SPD Language Concepts]</a>
<br><a href="slingshot-simulator">[⇢ Configuration of SPD with PCM]</a>
<br>
<br>
* 
* The *Slingshot Simulator* that has the necessary plugins for simulating PCM and SPD.
<br><a href="slingshot-simulator">[⇢ The Slingshot Simulator]</a>

The picture below shows a high-level overview of the approach and flow of activities.
<img src="images/overview.png" alt="slingshot-logo" width="500px" style="float:left; margin-right:20px;"/>
<h3>The Palladio Component Model for modelling static system configurations </h3>
<p>Other roles that exist in the Palladio development process model the system through the different static viewpoints (e.g., Component Repository, System Model, Resource and Allocation Model).
</p>
<a target="_blank" href="https://sdq.kastel.kit.edu/wiki/Palladio_Usecase_Tutorial">[↗ Tutorial]</a>

<h3>The SPD Modelling Language </h3>
<p>The <i>self-adaptive system architect</i> models the elasticity of the system through the SPD language. 
The SPD language allows defining policies that target different elements in the model, for example, a policy may target the infrastructure, or it may target one of the services. 
In addition, the SPD language features the following:
</p>
<ul>
<li>it allows to model different triggers based on stimuli that stems from the simulation (e.g., CPU utilization measurement data).</li>
<li>it allows to model different constraints which may be scoped for the policy or the target group (e.g., Cooldown Constraint for a policy, GroupSize Constraint for the target group)</li>
<li>it allows to model different types of adjustments (e.g., Step Adjustment of 1, everytime the policy is triggered one container is addedd)</li>
</ul>
<a href="tutorial">[⇢ Tutorial, Modelling]</a>

<h3>Simulating Elasticity Policies </h3>
Last but not least, the <i>self-adaptive system architect</i> evaluates the policies through the Slingshot simulator.
All the models are given as an input to the Slingshot simulator that simulates the system and provides the results to the <i>architect</i> for further analysis and refinement of the SPDs.
To be able to do so, the <i>architect</i> needs to create a mapping, through an auxiliary model (defined by another meta-model), of the SPD models and the static viewpoints of the system.
The mapping is done once and defines the target groups which could be used in the SPD models.
<a href="tutorial">[⇢ Tutorial, Analysis]</a>

