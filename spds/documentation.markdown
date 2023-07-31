---
layout: page
title: Documentation
parent: SPD Language
nav_order: 4
permalink: /docu/
---
<!-- This file was created using the HTML documentation generator. -->
<!-- Creation date: Tue Jul 25 10:18:12 CEST 2023-->
<html xmlns="http://www.w3.org/1999/xhtml">
	<head>
      	<title>Metamodel Documentation (platform:/resource/org.palladiosimulator.spd/model/SPD.ecore)</title>
    	<script type="text/javascript">
//<![CDATA[				    	
// TOC script based on code taken from http://www.quirksmode.org/dom/toc.html
function makeTOC() {

	var toc = document.createElement('div')				
	toc.id = "toc";
	toc.innerHTML = "Table of Contents"				
	document.body.appendChild(toc);
				
	var innertocDiv = createTOC()				
	toc.appendChild(innertocDiv);
}


function createTOC() {
var y = document.createElement('div');
y.id = 'innertoc';
//var a = y.appendChild(document.createElement('span'));
//a.onclick = showhideTOC;
//a.id = 'contentheader';
//a.innerHTML = 'Show Table of Contents';
var z = y.appendChild(document.createElement('div'));
//z.onclick = showhideTOC;
var toBeTOCced = getElementsByTagNames('h1,h2,h3');
if (toBeTOCced.length < 2) return false;
var hCount = 0;
var hhCount = 0;
var hhhCount = 0;
for (var i=0;i<toBeTOCced.length;i++) {
var tmp = document.createElement('a');
tmp.className = 'page';
var text;
var textPre;
if (toBeTOCced[i].nodeName == 'h2'){
tmp.className += ' indent';
textPre = hCount + "."+ ++hhCount + ". ";
}
else if (toBeTOCced[i].nodeName == 'h3'){
tmp.className += ' extraindent';
textPre = hCount + "."+ hhCount + "."+ ++hhhCount +". ";
}
else {
textPre = ++hCount + ". ";
hhCount = 0;
hhhCount = 0;
}
text = textPre + toBeTOCced[i].textContent;
toBeTOCced[i].innerHTML = textPre + toBeTOCced[i].innerHTML;

	tmp.innerHTML = text; 
	z.appendChild(tmp);
	var headerId = toBeTOCced[i].id || 'link' + i;
	tmp.href = '#' + headerId;
	toBeTOCced[i].id = headerId;
	}
	return y;
}

function getElementsByTagNames(list,obj) {
if (!obj) var obj = document;
var tagNames = list.split(',');
var resultArray = new Array();
for (var i=0;i<tagNames.length;i++) {
var tags = obj.getElementsByTagName(tagNames[i]);
for (var j=0;j<tags.length;j++) {
resultArray.push(tags[j]);
}
}
var testNode = resultArray[0];
if (!testNode) return [];
if (testNode.sourceIndex) {
resultArray.sort(function (a,b) {
return a.sourceIndex - b.sourceIndex;
});
}
else if (testNode.compareDocumentPosition) {
resultArray.sort(function (a,b) {
return 3 - (a.compareDocumentPosition(b) & 6);
});
}
return resultArray;
}

//]]>				    	
</script>
<link rel="stylesheet" type="text/css" href="https://raw.github.com/necolas/normalize.css/master/normalize.css" />
<style>
#toc {
position: fixed;
right: 0;
top: 0;
background-color:#eee;
overflow: scroll;
border: 1px dashed;
}

#toc #innertoc {
display: none;
height: 500px;
} /* Hide the full TOC by default */

#toc:hover #innertoc{
display: block; /* Show it on hover */
}
td {
}
.page{
display:table-row;
}
.indent {
text-indent:12pt;
}
.extraindent {
text-indent:14pt;
}

	    	</style>
	    	<link rel="stylesheet" type="text/css" href="style.css" />
	</head>
	<body onload="makeTOC();">
<h1 id="spd"><a href="#spd"><span class="packageName">spd</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">spd</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/1.0</span></div>
<h2 id="spdSPD"><a href="#spdSPD"><a href="#spdSPD">SPD</a></a></h2>

<p>The root elements that consists of all scaling policies under analysis for a given cloud application. The SPD is an Entity (PCM), it has a unique identifier and it has a name.  </p>
<h4><b>Supertype:</b><a href="#entityEntity">Entity</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="spdSPD.scalingPolicies" class="teletype">scalingPolicies</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#spdScalingPolicy">ScalingPolicy</a></span></div>
<div class="label">Cardinality: [1..*]</div>
<div class="label">Containment</div>
</td> 
<td> <p>The set of scaling policies under analysis for the given cloud application model.</p>
</td>
		</tr><tr>	<td><div id="spdSPD.targetGroups" class="teletype">targetGroups</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#targetsTargetGroup">TargetGroup</a></span></div>
<div class="label">Cardinality: [1..*]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr></table>
<a href="#spd.SPD.ref"></a>
<h2 id="spdScalingPolicy"><a href="#spdScalingPolicy"><a href="#spdScalingPolicy">ScalingPolicy</a></a></h2>

<p>A scaling policy determines the complete information for scaling a parituclar target. Each ScalingPolicy is an Entity (PCM), it has a unique identifier and it has a name.  </p>
<h4><b>Supertype:</b><a href="#entityEntity">Entity</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="spdScalingPolicy.active" class="teletype">active</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EBoolean</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#spd.ScalingPolicy.attr"></a>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="spdScalingPolicy.adjustmentType" class="teletype">adjustmentType</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#adjustmentsAdjustmentType">AdjustmentType</a></span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="spdScalingPolicy.policyConstraints" class="teletype">policyConstraints</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#constraintspolicyPolicyConstraint">PolicyConstraint</a></span></div>
<div class="label">Cardinality: [0..*]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="spdScalingPolicy.scalingTrigger" class="teletype">scalingTrigger</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersScalingTrigger">ScalingTrigger</a></span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="spdScalingPolicy.targetGroup" class="teletype">targetGroup</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#targetsTargetGroup">TargetGroup</a></span></div>
<div class="label">Cardinality: [1..1]</div>
</td> 
<td> </td>
		</tr></table>
<a href="#spd.ScalingPolicy.ref"></a>
<h1 id="targets"><a href="#targets"><span class="packageName">spd.targets</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">targets</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Targets/1.0</span></div>
<h2 id="targetsCompetingConsumersGroup"><a href="#targetsCompetingConsumersGroup"><a href="#targetsCompetingConsumersGroup">CompetingConsumersGroup</a></a></h2>

<h4><b>Supertype:</b><a href="#targetsTargetGroup">TargetGroup</a></h4><h2 id="targetsElasticInfrastructure"><a href="#targetsElasticInfrastructure"><a href="#targetsElasticInfrastructure">ElasticInfrastructure</a></a></h2>

<h4><b>Supertype:</b><a href="#targetsTargetGroup">TargetGroup</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="targetsElasticInfrastructure.PCM_ResourceEnvironment" class="teletype">PCM_ResourceEnvironment</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#resourceenvironmentResourceEnvironment">ResourceEnvironment</a></span></div>
<div class="label">Cardinality: [0..1]</div>
</td> 
<td> </td>
		</tr></table>
<a href="#targets.ElasticInfrastructure.ref"></a>
<h2 id="targetsServiceGroup"><a href="#targetsServiceGroup"><a href="#targetsServiceGroup">ServiceGroup</a></a></h2>

<h4><b>Supertype:</b><a href="#targetsTargetGroup">TargetGroup</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="targetsServiceGroup.unitAssembly" class="teletype">unitAssembly</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#compositionAssemblyContext">AssemblyContext</a></span></div>
<div class="label">Cardinality: [0..1]</div>
</td> 
<td> <p>The unitAssembly is used to point to the ServiceGroup in PCM. It is used also for disinguishing between different service groups. A prerequisite is that the unit assembly is already connected in a Service Group structure in PCM. </p>
</td>
		</tr></table>
<a href="#targets.ServiceGroup.ref"></a>
<h2 id="targetsTargetGroup"><a href="#targetsTargetGroup"><a href="#targetsTargetGroup">TargetGroup</a></a></h2>

<p>A TargetGroup defines a management group in SPD. It is both uniqely identified as well as it has a name, thus it extends from the Entity class of the PCM. </p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#entityEntity">Entity</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="targetsTargetGroup.targetConstraints" class="teletype">targetConstraints</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#constraintstargetTargetConstraint">TargetConstraint</a></span></div>
<div class="label">Cardinality: [0..*]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr></table>
<a href="#targets.TargetGroup.ref"></a>
<h1 id="adjustments"><a href="#adjustments"><span class="packageName">spd.adjustments</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">adjustments</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Adjustments/1.0</span></div>
<h2 id="adjustmentsAbsoluteAdjustment"><a href="#adjustmentsAbsoluteAdjustment"><a href="#adjustmentsAbsoluteAdjustment">AbsoluteAdjustment</a></a></h2>

<p>The AbsoluteAdjustment denotes that the group is adjusted to a goal value.</p>
<h4><b>Supertype:</b><a href="#adjustmentsAdjustmentType">AdjustmentType</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="adjustmentsAbsoluteAdjustment.goalValue" class="teletype">goalValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0</span></div>
 </td> <td><p>The goalValue determines the target number of elements for a particular group, e.g., a value 5 means that the group will have 5 elements.</p>
</td>
		</tr></table>
<a href="#adjustments.AbsoluteAdjustment.attr"></a>
<h2 id="adjustmentsAdjustmentType"><a href="#adjustmentsAdjustmentType"><a href="#adjustmentsAdjustmentType">AdjustmentType</a></a></h2>

<p>An AdjustmentType determines how the target group is adjusted upon the firing of a trigger.</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h2 id="adjustmentsRelativeAdjustment"><a href="#adjustmentsRelativeAdjustment"><a href="#adjustmentsRelativeAdjustment">RelativeAdjustment</a></a></h2>

<p>The RelativeAdjustment denotes that the group is adjusted relatively to the current number of elements. 
The RelativeAdjustment contains two parameters: the percentageGrowthValue and the minAdjustmentValue.
The percentageGrowthValue determines the change (increase/decrease) of the current capacity as a percentage value.
The minAdjustmentValue determines the minimal change of the current capacity.</p>
<h4><b>Supertype:</b><a href="#adjustmentsAdjustmentType">AdjustmentType</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="adjustmentsRelativeAdjustment.minAdjustmentValue" class="teletype">minAdjustmentValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0</span></div>
 </td> <td><p>A minimum adjustment value in case the percentage is 0. </p>
</td>
		</tr><tr>	<td><div id="adjustmentsRelativeAdjustment.percentageGrowthValue" class="teletype">percentageGrowthValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">100</span></div>
 </td> <td><p>The percantage value of adjustment e.g., a value of 10 denotes that 10% should be added to the existing capacity.</p>
</td>
		</tr></table>
<a href="#adjustments.RelativeAdjustment.attr"></a>
<h2 id="adjustmentsStepAdjustment"><a href="#adjustmentsStepAdjustment"><a href="#adjustmentsStepAdjustment">StepAdjustment</a></a></h2>

<p>The StepAdjustment denotes that the group is adjusted by adding or removing a fixed amount of elements.</p>
<h4><b>Supertype:</b><a href="#adjustmentsAdjustmentType">AdjustmentType</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="adjustmentsStepAdjustment.stepValue" class="teletype">stepValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0</span></div>
 </td> <td><p>The stepValue describes how many elements in the group should be added or removed. For example, a vallue of -1 determines that one element should be removed from the group.</p>
</td>
		</tr></table>
<a href="#adjustments.StepAdjustment.attr"></a>
<h1 id="constraints"><a href="#constraints"><span class="packageName">spd.constraints</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">constraints</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Constraints/1.0</span></div>
<h2 id="constraintsAbstractConstraint"><a href="#constraintsAbstractConstraint"><a href="#constraintsAbstractConstraint">AbstractConstraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#identifierIdentifier">Identifier</a></h4><h2 id="constraintsStateBasedContraint"><a href="#constraintsStateBasedContraint"><a href="#constraintsStateBasedContraint">StateBasedContraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#constraintsAbstractConstraint">AbstractConstraint</a></h4><h2 id="constraintsTemporalConstraint"><a href="#constraintsTemporalConstraint"><a href="#constraintsTemporalConstraint">TemporalConstraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#constraintsAbstractConstraint">AbstractConstraint</a></h4><h1 id="triggers"><a href="#triggers"><span class="packageName">spd.triggers</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">triggers</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Triggers/1.0</span></div>
<h2 id="triggersAGGREGATIONMETHOD"><a href="#triggersAGGREGATIONMETHOD"><a href="#triggersAGGREGATIONMETHOD">AGGREGATIONMETHOD</a></a></h2>

<p>Enum for the following aggregation methods: MIN, MAX, AVERAGE, SUM that are relevant for different triggers.</p>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">Literals</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Value</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>
	<td>
		<span class="teletype">AVERAGE</span>
	</td>
	<td>
		0
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">MAX</span>
	</td>
	<td>
		1
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">MIN</span>
	</td>
	<td>
		2
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">MEDIAN</span>
	</td>
	<td>
		3
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">SUM</span>
	</td>
	<td>
		4
	</td>
	<td>
	</td>	
</tr>
</table>
<a href="#triggers.AGGREGATIONMETHOD.lit"></a>
<h2 id="triggersBaseTrigger"><a href="#triggersBaseTrigger"><a href="#triggersBaseTrigger">BaseTrigger</a></a></h2>

<p>A BaseTrigger is a class of ScalingTrigger that works on a Stimulus (that entails the information gathered from the environment) and an ExpectedValue. Once the Stimulus 'matches' the ExpectedValue the trigger fires and an adjustment to the model is made. The matching of Stimulus with an ExpectedValue is determined by the subclasses. This can entail simple analysis through relational operators or more advanced transformation/aggregation of the Stimulus and the ExpectedValue. </p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#triggersScalingTrigger">ScalingTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersBaseTrigger.expectedValue" class="teletype">expectedValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#expectationsExpectedValue">ExpectedValue</a></span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="triggersBaseTrigger.stimulus" class="teletype">stimulus</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#stimuliStimulus">Stimulus</a></span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr></table>
<a href="#triggers.BaseTrigger.ref"></a>
<h2 id="triggersComposedTrigger"><a href="#triggersComposedTrigger"><a href="#triggersComposedTrigger">ComposedTrigger</a></a></h2>

<p>A ComposedTrigger composes two or more ScalingTriggers through a logical operator (i.e., AND, OR, XOR). This enables the defintion of composed triggers which encapsulate more advanced conditions on the state to fire the trigger. </p>
<h4><b>Supertype:</b><a href="#triggersScalingTrigger">ScalingTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersComposedTrigger.logicalOperator" class="teletype">logicalOperator</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersLogicalOperator">LogicalOperator</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#triggers.ComposedTrigger.attr"></a>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersComposedTrigger.scalingtrigger" class="teletype">scalingtrigger</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersScalingTrigger">ScalingTrigger</a></span></div>
<div class="label">Cardinality: [2..*]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr></table>
<a href="#triggers.ComposedTrigger.ref"></a>
<h2 id="triggersHDDUSAGETYPE"><a href="#triggersHDDUSAGETYPE"><a href="#triggersHDDUSAGETYPE">HDDUSAGETYPE</a></a></h2>

<p>Enum for the type of HDD usage: READ, WRITE</p>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">Literals</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Value</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>
	<td>
		<span class="teletype">READ</span>
	</td>
	<td>
		0
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">WRITE</span>
	</td>
	<td>
		1
	</td>
	<td>
	</td>	
</tr>
</table>
<a href="#triggers.HDDUSAGETYPE.lit"></a>
<h2 id="triggersLogicalOperator"><a href="#triggersLogicalOperator"><a href="#triggersLogicalOperator">LogicalOperator</a></a></h2>

<table>
<tr>
	<th colspan="3"><div class="tableHeader">Literals</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Value</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>
	<td>
		<span class="teletype">AND</span>
	</td>
	<td>
		0
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">OR</span>
	</td>
	<td>
		1
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">XOR</span>
	</td>
	<td>
		2
	</td>
	<td>
	</td>	
</tr>
</table>
<a href="#triggers.LogicalOperator.lit"></a>
<h2 id="triggersNETWORKUSAGETYPE"><a href="#triggersNETWORKUSAGETYPE"><a href="#triggersNETWORKUSAGETYPE">NETWORKUSAGETYPE</a></a></h2>

<p>Enum for the following Network Usage types: SEND, RECEIVE which are relevant to distinuish the type of use for a network resource.</p>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">Literals</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Value</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>
	<td>
		<span class="teletype">SEND</span>
	</td>
	<td>
		0
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">RECEIVE</span>
	</td>
	<td>
		1
	</td>
	<td>
	</td>	
</tr>
</table>
<a href="#triggers.NETWORKUSAGETYPE.lit"></a>
<h2 id="triggersRelationalOperator"><a href="#triggersRelationalOperator"><a href="#triggersRelationalOperator">RelationalOperator</a></a></h2>

<table>
<tr>
	<th colspan="3"><div class="tableHeader">Literals</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Value</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>
	<td>
		<span class="teletype">LessThan</span>
	</td>
	<td>
		0
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">GreaterThan</span>
	</td>
	<td>
		1
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">EqualTo</span>
	</td>
	<td>
		2
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">LessThanOrEqualTo</span>
	</td>
	<td>
		3
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">GreaterThanOrEqualTo</span>
	</td>
	<td>
		4
	</td>
	<td>
	</td>	
</tr>
</table>
<a href="#triggers.RelationalOperator.lit"></a>
<h2 id="triggersScalingTrigger"><a href="#triggersScalingTrigger"><a href="#triggersScalingTrigger">ScalingTrigger</a></a></h2>

<p>The ScalingTrigger is a core concept in SPD. It entails both the information that is fetched from the simulation and models as well as the type of analysis that is performed on that information. It is uniquely identified as it extends from Idenfier (PCM).</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#identifierIdentifier">Identifier</a></h4><h2 id="triggersSimpleFireOnTrend"><a href="#triggersSimpleFireOnTrend"><a href="#triggersSimpleFireOnTrend">SimpleFireOnTrend</a></a></h2>

<p>The SimpleFireOnTrend trigger is a more advanced trigger that aggregates values and determines a trend and fires whenever this trend is as an expectedTrend value. </p>
<h4><b>Supertype:</b><a href="#triggersBaseTrigger">BaseTrigger</a></h4><h2 id="triggersSimpleFireOnValue"><a href="#triggersSimpleFireOnValue"><a href="#triggersSimpleFireOnValue">SimpleFireOnValue</a></a></h2>

<p>The SimpleFireOnValue trigger the most simplistic BaseTrigger that works on the fed stimulus through a relational operator with an expected value. In case 'LessThen' is specified then the the trigger will fire upon stiumuls &lt; expectedValue. </p>
<h4><b>Supertype:</b><a href="#triggersBaseTrigger">BaseTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersSimpleFireOnValue.relationalOperator" class="teletype">relationalOperator</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersRelationalOperator">RelationalOperator</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#triggers.SimpleFireOnValue.attr"></a>
<h2 id="triggersTrendPattern"><a href="#triggersTrendPattern"><a href="#triggersTrendPattern">TrendPattern</a></a></h2>

<table>
<tr>
	<th colspan="3"><div class="tableHeader">Literals</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Value</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>
	<td>
		<span class="teletype">Increasing</span>
	</td>
	<td>
		0
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">Decreasing</span>
	</td>
	<td>
		1
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">NonIncreasing</span>
	</td>
	<td>
		2
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">NonDecreasing</span>
	</td>
	<td>
		3
	</td>
	<td>
	</td>	
</tr>
</table>
<a href="#triggers.TrendPattern.lit"></a>
<h1 id="constraintspolicy"><a href="#constraintspolicy"><span class="packageName">spd.constraints.policy</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">constraints.policy</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Constraints/Policy/1.0</span></div>
<h2 id="constraintspolicyCooldownConstraint"><a href="#constraintspolicyCooldownConstraint"><a href="#constraintspolicyCooldownConstraint">CooldownConstraint</a></a></h2>

<p>The CoolDown constraint defines a quiescence period in which the target group is not enacted by the policy. 
In addition one can specify the maximum number of scaling operations that can occur in the defined quiescence period. 
Contrary to the IntervalConstraint, the CooldownConstraint determines the future enactment of the policy after an adjustment has happened.</p>
<h4><b>Supertypes:</b><a href="#constraintspolicyPolicyConstraint">PolicyConstraint</a>, <a href="#constraintsTemporalConstraint">TemporalConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="constraintspolicyCooldownConstraint.cooldownTime" class="teletype">cooldownTime</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr><tr>	<td><div id="constraintspolicyCooldownConstraint.maxScalingOperations" class="teletype">maxScalingOperations</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0</span></div>
 </td> <td></td>
		</tr></table>
<a href="#constraints.policy.CooldownConstraint.attr"></a>
<h2 id="constraintspolicyIntervalConstraint"><a href="#constraintspolicyIntervalConstraint"><a href="#constraintspolicyIntervalConstraint">IntervalConstraint</a></a></h2>

<p>The IntervalConstraint identifies fixed intervals in which a policy enacts adjustments. Contrary to the CooldownConstraint, the IntervalConstraint predefines the enactment of the policy in time. </p>
<h4><b>Supertypes:</b><a href="#constraintspolicyPolicyConstraint">PolicyConstraint</a>, <a href="#constraintsTemporalConstraint">TemporalConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="constraintspolicyIntervalConstraint.intervalDuration" class="teletype">intervalDuration</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td><p>The duration in which no enactment by the policy occurs. </p>
</td>
		</tr><tr>	<td><div id="constraintspolicyIntervalConstraint.offset" class="teletype">offset</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td><p>The offset determines a period of time from which the interval constraint should begin. </p>
</td>
		</tr><tr>	<td><div id="constraintspolicyIntervalConstraint.repeat" class="teletype">repeat</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EBoolean</span></div>
<div class="label">Cardinality: [0..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">false</span></div>
 </td> <td><p>The repeat property determines whether the interval constraint should repeat throughout the simulation or is applied once, which is the default case (false).</p>
</td>
		</tr></table>
<a href="#constraints.policy.IntervalConstraint.attr"></a>
<h2 id="constraintspolicyPolicyConstraint"><a href="#constraintspolicyPolicyConstraint"><a href="#constraintspolicyPolicyConstraint">PolicyConstraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#constraintsAbstractConstraint">AbstractConstraint</a></h4><h1 id="constraintstarget"><a href="#constraintstarget"><span class="packageName">spd.constraints.target</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">constraints.target</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Constraints/Target/1.0</span></div>
<h2 id="constraintstargetTargetConstraint"><a href="#constraintstargetTargetConstraint"><a href="#constraintstargetTargetConstraint">TargetConstraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#constraintsAbstractConstraint">AbstractConstraint</a></h4><h2 id="constraintstargetTargetGroupSizeConstraint"><a href="#constraintstargetTargetGroupSizeConstraint"><a href="#constraintstargetTargetGroupSizeConstraint">TargetGroupSizeConstraint</a></a></h2>

<h4><b>Supertypes:</b><a href="#constraintsStateBasedContraint">StateBasedContraint</a>, <a href="#constraintstargetTargetConstraint">TargetConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="constraintstargetTargetGroupSizeConstraint.maxSize" class="teletype">maxSize</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr><tr>	<td><div id="constraintstargetTargetGroupSizeConstraint.minSize" class="teletype">minSize</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#constraints.target.TargetGroupSizeConstraint.attr"></a>
<h2 id="constraintstargetThrashingConstraint"><a href="#constraintstargetThrashingConstraint"><a href="#constraintstargetThrashingConstraint">ThrashingConstraint</a></a></h2>

<p>Thrashing constraint is used to constraint the thrashing of resources i.e. increase and decrease of resources. The constraint is defined by the minimum amount of time where no two decicions with adjustments in two oposite directions can occur. </p>
<h4><b>Supertypes:</b><a href="#constraintstargetTargetConstraint">TargetConstraint</a>, <a href="#constraintsTemporalConstraint">TemporalConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="constraintstargetThrashingConstraint.minimumTimeNoThrashing" class="teletype">minimumTimeNoThrashing</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#constraints.target.ThrashingConstraint.attr"></a>
</body>
</html>


