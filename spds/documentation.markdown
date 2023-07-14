---
layout: page
title: Documentation
parent: SPD Language
nav_order: 4
permalink: /docu/
---
<!-- This file was created using the HTML documentation generator. -->
<!-- Creation date: Fri Jul 14 11:58:46 CEST 2023-->
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
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#policyPolicyConstraint">PolicyConstraint</a></span></div>
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
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#targetTargetConstraint">TargetConstraint</a></span></div>
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
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersexpectationsExpectedValue">ExpectedValue</a></span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="triggersBaseTrigger.stimulus" class="teletype">stimulus</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersstimuliStimulus">Stimulus</a></span></div>
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
<h1 id="policy"><a href="#policy"><span class="packageName">spd.constraints.policy</span> package</a></h1>

<p>The policy subpackage encapsulates constraints that are applicable to the scope of a policy. </p>
<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">policy</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Constraints/Policy/1.0</span></div>
<h2 id="policyCooldownConstraint"><a href="#policyCooldownConstraint"><a href="#policyCooldownConstraint">CooldownConstraint</a></a></h2>

<p>The CoolDown constraint defines a quiescence period in which the target group is not enacted by the policy. 
In addition one can specify the maximum number of scaling operations that can occur in the defined quiescence period. 
Contrary to the IntervalConstraint, the CooldownConstraint determines the future enactment of the policy after an adjustment has happened.</p>
<h4><b>Supertype:</b><a href="#constraintsTemporalConstraint">TemporalConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="policyCooldownConstraint.cooldownTime" class="teletype">cooldownTime</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr><tr>	<td><div id="policyCooldownConstraint.maxScalingOperations" class="teletype">maxScalingOperations</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#policy.CooldownConstraint.attr"></a>
<h2 id="policyIntervallConstraint"><a href="#policyIntervallConstraint"><a href="#policyIntervallConstraint">IntervallConstraint</a></a></h2>

<p>The IntervalConstraint identifies fixed intervals in which a policy enacts adjustments. Contrary to the CooldownConstraint, the IntervalConstraint predefines the enactment of the policy in time. </p>
<h4><b>Supertypes:</b><a href="#policyPolicyConstraint">PolicyConstraint</a>, <a href="#constraintsTemporalConstraint">TemporalConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="policyIntervallConstraint.intervallDuration" class="teletype">intervallDuration</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td><p>The duration in which no enactment by the policy occurs. </p>
</td>
		</tr><tr>	<td><div id="policyIntervallConstraint.offset" class="teletype">offset</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td><p>The offset determines a period of time from which the interval constraint should begin. </p>
</td>
		</tr></table>
<a href="#policy.IntervallConstraint.attr"></a>
<h2 id="policyPolicyConstraint"><a href="#policyPolicyConstraint"><a href="#policyPolicyConstraint">PolicyConstraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#constraintsAbstractConstraint">AbstractConstraint</a></h4><h1 id="target"><a href="#target"><span class="packageName">spd.constraints.target</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">target</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Constraints/Target/1.0</span></div>
<h2 id="targetTargetConstraint"><a href="#targetTargetConstraint"><a href="#targetTargetConstraint">TargetConstraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#constraintsAbstractConstraint">AbstractConstraint</a></h4><h2 id="targetTargetGroupSizeConstraint"><a href="#targetTargetGroupSizeConstraint"><a href="#targetTargetGroupSizeConstraint">TargetGroupSizeConstraint</a></a></h2>

<h4><b>Supertypes:</b><a href="#constraintsStateBasedContraint">StateBasedContraint</a>, <a href="#targetTargetConstraint">TargetConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="targetTargetGroupSizeConstraint.maxSize" class="teletype">maxSize</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr><tr>	<td><div id="targetTargetGroupSizeConstraint.minSize" class="teletype">minSize</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#target.TargetGroupSizeConstraint.attr"></a>
<h2 id="targetThrashingConstraint"><a href="#targetThrashingConstraint"><a href="#targetThrashingConstraint">ThrashingConstraint</a></a></h2>

<p>Thrashing constraint is used to constraint the thrashing of resources i.e. increase and decrease of resources. The constraint is defined by the minimum amount of time where no two decicions with adjustments in two oposite directions can occur. </p>
<h4><b>Supertypes:</b><a href="#targetTargetConstraint">TargetConstraint</a>, <a href="#constraintsTemporalConstraint">TemporalConstraint</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="targetThrashingConstraint.minimumTimeNoThrashing" class="teletype">minimumTimeNoThrashing</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#target.ThrashingConstraint.attr"></a>
<h1 id="triggersstimuli"><a href="#triggersstimuli"><span class="packageName">spd.triggers.stimuli</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">triggers.stimuli</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Triggers/Stimuli/1.0</span></div>
<h2 id="triggersstimuliCPUUtilization"><a href="#triggersstimuliCPUUtilization"><a href="#triggersstimuliCPUUtilization">CPUUtilization</a></a></h2>

<p>A resource utilization based stimulus based on the CPU resource.</p>
<h4><b>Supertype:</b><a href="#triggersstimuliResourceUtilizationStimulus">ResourceUtilizationStimulus</a></h4><h2 id="triggersstimuliHDDUtilization"><a href="#triggersstimuliHDDUtilization"><a href="#triggersstimuliHDDUtilization">HDDUtilization</a></a></h2>

<p>A resource utilization based stimulus based on the HDD resource.</p>
<h4><b>Supertype:</b><a href="#triggersstimuliResourceUtilizationStimulus">ResourceUtilizationStimulus</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersstimuliHDDUtilization.usageType" class="teletype">usageType</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersHDDUSAGETYPE">HDDUSAGETYPE</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#triggers.stimuli.HDDUtilization.attr"></a>
<h2 id="triggersstimuliManagedElementsStateStimulus"><a href="#triggersstimuliManagedElementsStateStimulus"><a href="#triggersstimuliManagedElementsStateStimulus">ManagedElementsStateStimulus</a></a></h2>

<p>The ManagedElementsStateStiumlus classifies the stimuli that has the source in the managed elements. A ManagedElementsStateStimulus has to specify how the aggregation across elements is performed.</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#triggersstimuliTargetGroupStateStimulus">TargetGroupStateStimulus</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersstimuliManagedElementsStateStimulus.aggregationOverElements" class="teletype">aggregationOverElements</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersAGGREGATIONMETHOD">AGGREGATIONMETHOD</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td><p>The aggregation accross different resource containers in the Target Group. For example if two containers C1 and C2 have a resource utilizaiton of 0.6, respectively 0.8, then choosing AVERAGE as an aggreagtion method then it determines that the value of 0.7 should be compared against the threshold value. </p>
</td>
		</tr></table>
<a href="#triggers.stimuli.ManagedElementsStateStimulus.attr"></a>
<h2 id="triggersstimuliMemoryUtilization"><a href="#triggersstimuliMemoryUtilization"><a href="#triggersstimuliMemoryUtilization">MemoryUtilization</a></a></h2>

<p>A resource utilization based stimulus based on the memory resource.</p>
<h4><b>Supertype:</b><a href="#triggersstimuliResourceUtilizationStimulus">ResourceUtilizationStimulus</a></h4><h2 id="triggersstimuliNetworkUtilization"><a href="#triggersstimuliNetworkUtilization"><a href="#triggersstimuliNetworkUtilization">NetworkUtilization</a></a></h2>

<p>If the link has been modelled with a certain capacity, then the NetworkUtilization of a certain type determines the fraction of that capacity that is being used by the elements of the target group. </p>
<h4><b>Supertype:</b><a href="#triggersstimuliResourceUtilizationStimulus">ResourceUtilizationStimulus</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersstimuliNetworkUtilization.usageType" class="teletype">usageType</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersNETWORKUSAGETYPE">NETWORKUSAGETYPE</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td><p>The type of network usage.</p>
</td>
		</tr></table>
<a href="#triggers.stimuli.NetworkUtilization.attr"></a>
<h2 id="triggersstimuliNumberOfElements"><a href="#triggersstimuliNumberOfElements"><a href="#triggersstimuliNumberOfElements">NumberOfElements</a></a></h2>

<p>The NumberOfElements is a concrete stimulus that represents the number of elements in the target group. </p>
<h4><b>Supertype:</b><a href="#triggersstimuliTargetGroupStateStimulus">TargetGroupStateStimulus</a></h4><h2 id="triggersstimuliOperationResponseTime"><a href="#triggersstimuliOperationResponseTime"><a href="#triggersstimuliOperationResponseTime">OperationResponseTime</a></a></h2>

<p>A stimulus based on the response time of a given operation. It requires specifying the operationSignature.</p>
<h4><b>Supertype:</b><a href="#triggersstimuliSourceInterfaceStimulus">SourceInterfaceStimulus</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersstimuliOperationResponseTime.operationSignature" class="teletype">operationSignature</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#repositoryOperationSignature">OperationSignature</a></span></div>
<div class="label">Cardinality: [0..1]</div>
</td> 
<td> <p>The operation from which the response time is used. </p>
</td>
		</tr></table>
<a href="#triggers.stimuli.OperationResponseTime.ref"></a>
<h2 id="triggersstimuliQueueLength"><a href="#triggersstimuliQueueLength"><a href="#triggersstimuliQueueLength">QueueLength</a></a></h2>

<p>A queue length based stimulus from the source of the target group. A precondition is that the target group is of type CompetingConsumers. </p>
<h4><b>Supertype:</b><a href="#triggersstimuliSourceInterfaceStimulus">SourceInterfaceStimulus</a></h4><h2 id="triggersstimuliResourceUtilizationStimulus"><a href="#triggersstimuliResourceUtilizationStimulus"><a href="#triggersstimuliResourceUtilizationStimulus">ResourceUtilizationStimulus</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#triggersstimuliManagedElementsStateStimulus">ManagedElementsStateStimulus</a></h4><h2 id="triggersstimuliSimulationStateStimulus"><a href="#triggersstimuliSimulationStateStimulus"><a href="#triggersstimuliSimulationStateStimulus">SimulationStateStimulus</a></a></h2>

<p>The SimulationStateStimulus classifies all stimuli that has the source from the simulation state. A direct subclass is for example the SimulationTime stimulus. </p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#triggersstimuliStimulus">Stimulus</a></h4><h2 id="triggersstimuliSimulationTime"><a href="#triggersstimuliSimulationTime"><a href="#triggersstimuliSimulationTime">SimulationTime</a></a></h2>

<p>A stimulus based on the simulation time.</p>
<h4><b>Supertype:</b><a href="#triggersstimuliSimulationStateStimulus">SimulationStateStimulus</a></h4><h2 id="triggersstimuliSourceInterfaceStimulus"><a href="#triggersstimuliSourceInterfaceStimulus"><a href="#triggersstimuliSourceInterfaceStimulus">SourceInterfaceStimulus</a></a></h2>

<p>The SourceInterfaceStimulus encapsulates all stimuli that is comming from the source of the target group. For example, in case of a load balanced service then the operation response time is a stimulus that</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#triggersstimuliStimulus">Stimulus</a></h4><h2 id="triggersstimuliStimulus"><a href="#triggersstimuliStimulus"><a href="#triggersstimuliStimulus">Stimulus</a></a></h2>

<p>The Stimulus defines observable information during the simulation of an architectural model upon which a trigger can fire. Each Stimulus </p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h2 id="triggersstimuliTargetGroupStateStimulus"><a href="#triggersstimuliTargetGroupStateStimulus"><a href="#triggersstimuliTargetGroupStateStimulus">TargetGroupStateStimulus</a></a></h2>

<p>The TargetGroupStateStimulus classifies all stimuli that has the source from the elements that are being adjusted by the policy. </p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#triggersstimuliStimulus">Stimulus</a></h4><h2 id="triggersstimuliTaskCount"><a href="#triggersstimuliTaskCount"><a href="#triggersstimuliTaskCount">TaskCount</a></a></h2>

<p>The TaskCount stimulus is a concrete stimulus that represents the number of tasks that are currently being processed by the managed elements.</p>
<h4><b>Supertype:</b><a href="#triggersstimuliManagedElementsStateStimulus">ManagedElementsStateStimulus</a></h4><h1 id="triggersexpectations"><a href="#triggersexpectations"><span class="packageName">spd.triggers.expectations</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">triggers.expectations</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://palladiosimulator.org/ScalingPolicyDefinition/Triggers/Expectations/1.0</span></div>
<h2 id="triggersexpectationsExpectedCount"><a href="#triggersexpectationsExpectedCount"><a href="#triggersexpectationsExpectedCount">ExpectedCount</a></a></h2>

<h4><b>Supertype:</b><a href="#triggersexpectationsExpectedPrimitive">ExpectedPrimitive</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersexpectationsExpectedCount.count" class="teletype">count</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#triggers.expectations.ExpectedCount.attr"></a>
<h2 id="triggersexpectationsExpectedPercentage"><a href="#triggersexpectationsExpectedPercentage"><a href="#triggersexpectationsExpectedPercentage">ExpectedPercentage</a></a></h2>

<h4><b>Supertype:</b><a href="#triggersexpectationsExpectedPrimitive">ExpectedPrimitive</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersexpectationsExpectedPercentage.value" class="teletype">value</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#triggers.expectations.ExpectedPercentage.attr"></a>
<h2 id="triggersexpectationsExpectedPrimitive"><a href="#triggersexpectationsExpectedPrimitive"><a href="#triggersexpectationsExpectedPrimitive">ExpectedPrimitive</a></a></h2>

<p>There are three different primitives in the context of triggers: percentages, time, and count.</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#triggersexpectationsExpectedValue">ExpectedValue</a></h4><h2 id="triggersexpectationsExpectedTime"><a href="#triggersexpectationsExpectedTime"><a href="#triggersexpectationsExpectedTime">ExpectedTime</a></a></h2>

<h4><b>Supertype:</b><a href="#triggersexpectationsExpectedPrimitive">ExpectedPrimitive</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersexpectationsExpectedTime.value" class="teletype">value</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#triggers.expectations.ExpectedTime.attr"></a>
<h2 id="triggersexpectationsExpectedTrend"><a href="#triggersexpectationsExpectedTrend"><a href="#triggersexpectationsExpectedTrend">ExpectedTrend</a></a></h2>

<h4><b>Supertype:</b><a href="#triggersexpectationsExpectedValue">ExpectedValue</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="triggersexpectationsExpectedTrend.trend" class="teletype">trend</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#triggersTrendPattern">TrendPattern</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#triggers.expectations.ExpectedTrend.attr"></a>
<h2 id="triggersexpectationsExpectedValue"><a href="#triggersexpectationsExpectedValue"><a href="#triggersexpectationsExpectedValue">ExpectedValue</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h2 id="triggersexpectationsNoExpectation"><a href="#triggersexpectationsNoExpectation"><a href="#triggersexpectationsNoExpectation">NoExpectation</a></a></h2>

<h4><b>Supertype:</b><a href="#triggersexpectationsExpectedValue">ExpectedValue</a></h4></body>
</html>

