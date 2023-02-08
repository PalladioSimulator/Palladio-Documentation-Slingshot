---
layout: page
title: Documentation
parent: SPD Language
nav_order: 4
permalink: /docu/
---
<!-- This file was created using the HTML documentation generator. -->
<!-- Creation date: Sat Jun 11 11:07:24 CEST 2022-->
<html xmlns="http://www.w3.org/1999/xhtml">
	<head>
      	<title>Metamodel Documentation (platform:/resource/ScalingMetaModel/model/SPD.ecore)</title>
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
<h1 id="deunistuttgartsqaslingshotspd"><a href="#deunistuttgartsqaslingshotspd"><span class="packageName">spd</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">de.unistuttgart.sqa.slingshot.spd</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://de/unistuttgart/sqa/slingshot/spd</span></div>
<h2 id="deunistuttgartsqaslingshotspdNamedElement"><a href="#deunistuttgartsqaslingshotspdNamedElement"><a href="#deunistuttgartsqaslingshotspdNamedElement">NamedElement</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdNamedElement.name" class="teletype">name</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EString</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.NamedElement.attr"></a>
<h2 id="deunistuttgartsqaslingshotspdSPD"><a href="#deunistuttgartsqaslingshotspdSPD"><a href="#deunistuttgartsqaslingshotspdSPD">SPD</a></a></h2>

<p>The root elements that consists of all scaling policies under analysis for a given cloud application.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdNamedElement">NamedElement</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdSPD.scalingPolicies" class="teletype">scalingPolicies</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdScalingPolicy">ScalingPolicy</a></span></div>
<div class="label">Cardinality: [1..*]</div>
<div class="label">Containment</div>
</td> 
<td> <p>The set of scaling policies under analysis for the given cloud application model.</p>
</td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdSPD.targetGroups" class="teletype">targetGroups</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtargetsTargetGroup">TargetGroup</a></span></div>
<div class="label">Cardinality: [1..*]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.SPD.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdScalingPolicy"><a href="#deunistuttgartsqaslingshotspdScalingPolicy"><a href="#deunistuttgartsqaslingshotspdScalingPolicy">ScalingPolicy</a></a></h2>

<p>A scaling policy determines the complete information for scaling a parituclar target. It is a containment of a trigger and an adjustment type. It references a target group which is adjusted when the trigger fires.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdNamedElement">NamedElement</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdScalingPolicy.active" class="teletype">active</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EBoolean</span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.ScalingPolicy.attr"></a>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdScalingPolicy.adjustmentType" class="teletype">adjustmentType</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdadjustmentsAdjustmentType">AdjustmentType</a></span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdScalingPolicy.policyConstraints" class="teletype">policyConstraints</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdconstraintspolicyPolicyConstraint">PolicyConstraint</a></span></div>
<div class="label">Cardinality: [0..*]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdScalingPolicy.scalingTrigger" class="teletype">scalingTrigger</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersScalingTrigger">ScalingTrigger</a></span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdScalingPolicy.targetGroup" class="teletype">targetGroup</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtargetsTargetGroup">TargetGroup</a></span></div>
<div class="label">Cardinality: [1..1]</div>
</td> 
<td> </td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.ScalingPolicy.ref"></a>
<h1 id="deunistuttgartsqaslingshotspdtargets"><a href="#deunistuttgartsqaslingshotspdtargets"><span class="packageName">spd.targets</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">de.unistuttgart.sqa.slingshot.spd.targets</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://de/unistuttgart/sqa/slingshot/spd/targets</span></div>
<h2 id="deunistuttgartsqaslingshotspdtargetsElasticInfrastructure"><a href="#deunistuttgartsqaslingshotspdtargetsElasticInfrastructure"><a href="#deunistuttgartsqaslingshotspdtargetsElasticInfrastructure">ElasticInfrastructure</a></a></h2>

<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtargetsTargetGroup">TargetGroup</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtargetsElasticInfrastructure.PCM_ResourceEnvironment" class="teletype">PCM_ResourceEnvironment</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"></span></div>
<div class="label">Cardinality: [0..1]</div>
</td> 
<td> </td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.targets.ElasticInfrastructure.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdtargetsElasticQueue"><a href="#deunistuttgartsqaslingshotspdtargetsElasticQueue"><a href="#deunistuttgartsqaslingshotspdtargetsElasticQueue">ElasticQueue</a></a></h2>

<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtargetsTargetGroup">TargetGroup</a></h4><h2 id="deunistuttgartsqaslingshotspdtargetsElasticService"><a href="#deunistuttgartsqaslingshotspdtargetsElasticService"><a href="#deunistuttgartsqaslingshotspdtargetsElasticService">ElasticService</a></a></h2>

<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtargetsTargetGroup">TargetGroup</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtargetsElasticService.PCM_AssemblyContext" class="teletype">PCM_AssemblyContext</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"></span></div>
<div class="label">Cardinality: [0..1]</div>
</td> 
<td> </td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.targets.ElasticService.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdtargetsTargetGroup"><a href="#deunistuttgartsqaslingshotspdtargetsTargetGroup"><a href="#deunistuttgartsqaslingshotspdtargetsTargetGroup">TargetGroup</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdNamedElement">NamedElement</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtargetsTargetGroup.targetConstraints" class="teletype">targetConstraints</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdconstraintstargetTargetConstraint">TargetConstraint</a></span></div>
<div class="label">Cardinality: [0..*]</div>
<div class="label">Containment</div>
</td> 
<td> </td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.targets.TargetGroup.ref"></a>
<h1 id="deunistuttgartsqaslingshotspdadjustments"><a href="#deunistuttgartsqaslingshotspdadjustments"><span class="packageName">spd.adjustments</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">de.unistuttgart.sqa.slingshot.spd.adjustments</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://de/unistuttgart/sqa/slingshot/spd/adjustments</span></div>
<h2 id="deunistuttgartsqaslingshotspdadjustmentsAbsoluteAdjustment"><a href="#deunistuttgartsqaslingshotspdadjustmentsAbsoluteAdjustment"><a href="#deunistuttgartsqaslingshotspdadjustmentsAbsoluteAdjustment">AbsoluteAdjustment</a></a></h2>

<p>The AbsoluteAdjustment denotes that the group is adjusted to a goal value.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdadjustmentsAdjustmentType">AdjustmentType</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdadjustmentsAbsoluteAdjustment.goalValue" class="teletype">goalValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0</span></div>
 </td> <td><p>The goalValue determines the target number of elements for a particular group, e.g., a value 5 means that the group will have 5 elements.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.adjustments.AbsoluteAdjustment.attr"></a>
<h2 id="deunistuttgartsqaslingshotspdadjustmentsAdjustmentType"><a href="#deunistuttgartsqaslingshotspdadjustmentsAdjustmentType"><a href="#deunistuttgartsqaslingshotspdadjustmentsAdjustmentType">AdjustmentType</a></a></h2>

<p>An Adjustment Type determines how the target group is adjusted. </p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h2 id="deunistuttgartsqaslingshotspdadjustmentsRelativeAdjustment"><a href="#deunistuttgartsqaslingshotspdadjustmentsRelativeAdjustment"><a href="#deunistuttgartsqaslingshotspdadjustmentsRelativeAdjustment">RelativeAdjustment</a></a></h2>

<p>The RelativeAdjustment denotes that the group should is adjusted relatively to the current number of elements.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdadjustmentsAdjustmentType">AdjustmentType</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdadjustmentsRelativeAdjustment.minAdjustmentValue" class="teletype">minAdjustmentValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0</span></div>
 </td> <td><p>A minimum adjustment value in case the percentage is 0. </p>
</td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdadjustmentsRelativeAdjustment.percentageValue" class="teletype">percentageValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0.0</span></div>
 </td> <td><p>The percantage value of adjustment e.g., a value of 10 denotes that 10% should be added to the existing capacity.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.adjustments.RelativeAdjustment.attr"></a>
<h2 id="deunistuttgartsqaslingshotspdadjustmentsStepAdjustment"><a href="#deunistuttgartsqaslingshotspdadjustmentsStepAdjustment"><a href="#deunistuttgartsqaslingshotspdadjustmentsStepAdjustment">StepAdjustment</a></a></h2>

<p>The StepAdjustment denotes that the group is adjusted by adding or removing a fixed amount of elements.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdadjustmentsAdjustmentType">AdjustmentType</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdadjustmentsStepAdjustment.stepValue" class="teletype">stepValue</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EInt</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0</span></div>
 </td> <td><p>The stepValue describes how many elements in the group should be added or removed. For example, a vallue of -1 determines that one element should be removed from the group.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.adjustments.StepAdjustment.attr"></a>
<h1 id="deunistuttgartsqaslingshotspdconstraints"><a href="#deunistuttgartsqaslingshotspdconstraints"><span class="packageName">spd.constraints</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">de.unistuttgart.sqa.slingshot.spd.constraints</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://de/unistuttgart/sqa/slingshot/spd/constraints</span></div>
<h2 id="deunistuttgartsqaslingshotspdconstraintsAbstractConstraint"><a href="#deunistuttgartsqaslingshotspdconstraintsAbstractConstraint"><a href="#deunistuttgartsqaslingshotspdconstraintsAbstractConstraint">AbstractConstraint</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h1 id="deunistuttgartsqaslingshotspdtriggers"><a href="#deunistuttgartsqaslingshotspdtriggers"><span class="packageName">spd.triggers</span> package</a></h1>

<div class="">EPackage properties:</div>
<div class="keyValue"><span class="label">Namespace Prefix: </span><span class="teletype">de.unistuttgart.sqa.slingshot.spd.triggers</span></div>
<div class="keyValue"><span class="label">Namespace URI: </span><span class="teletype">http://de/unistuttgart/sqa/slingshot/spd/triggers</span></div>
<h2 id="deunistuttgartsqaslingshotspdtriggersAGGREGATIONMETHOD"><a href="#deunistuttgartsqaslingshotspdtriggersAGGREGATIONMETHOD"><a href="#deunistuttgartsqaslingshotspdtriggersAGGREGATIONMETHOD">AGGREGATIONMETHOD</a></a></h2>

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
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.AGGREGATIONMETHOD.lit"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersCPUUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersCPUUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersCPUUtilizationTrigger">CPUUtilizationTrigger</a></a></h2>

<p>A utilization based trigger based on the CPU resource.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger">ProcessingResourceUtilizationBasedTrigger</a></h4><h2 id="deunistuttgartsqaslingshotspdtriggersHDDUSAGETYPE"><a href="#deunistuttgartsqaslingshotspdtriggersHDDUSAGETYPE"><a href="#deunistuttgartsqaslingshotspdtriggersHDDUSAGETYPE">HDDUSAGETYPE</a></a></h2>

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
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.HDDUSAGETYPE.lit"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersHDDUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersHDDUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersHDDUtilizationTrigger">HDDUtilizationTrigger</a></a></h2>

<p>A utilization based trigger based on the HDD resource.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger">ProcessingResourceUtilizationBasedTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersHDDUtilizationTrigger.usageType" class="teletype">usageType</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersHDDUSAGETYPE">HDDUSAGETYPE</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.HDDUtilizationTrigger.attr"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersIdleTimeTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersIdleTimeTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersIdleTimeTrigger">IdleTimeTrigger</a></a></h2>

<p>IdleTimeTrigger bases the trigger on the idle time of a resource container.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersTimeBasedTrigger">TimeBasedTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersIdleTimeTrigger.resourceContainer" class="teletype">resourceContainer</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"></span></div>
<div class="label">Cardinality: [0..*]</div>
</td> 
<td> <p>Resource containers that are checked for being idle.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.IdleTimeTrigger.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersNETWORKUSAGETYPE"><a href="#deunistuttgartsqaslingshotspdtriggersNETWORKUSAGETYPE"><a href="#deunistuttgartsqaslingshotspdtriggersNETWORKUSAGETYPE">NETWORKUSAGETYPE</a></a></h2>

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
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.NETWORKUSAGETYPE.lit"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersNetworkUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersNetworkUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersNetworkUtilizationTrigger">NetworkUtilizationTrigger</a></a></h2>

<p>NetworkUtilizationTrigger is a specialized ResourceUtilizationBasedTrigger that bases the trigger on the utilization of the network link as specified by the linkingResource.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersResourceUtilizationBasedTrigger">ResourceUtilizationBasedTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersNetworkUtilizationTrigger.usageType" class="teletype">usageType</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersNETWORKUSAGETYPE">NETWORKUSAGETYPE</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td><p>The type of network usage.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.NetworkUtilizationTrigger.attr"></a>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersNetworkUtilizationTrigger.linkingResource" class="teletype">linkingResource</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"></span></div>
<div class="label">Cardinality: [0..*]</div>
</td> 
<td> <p>The specific linking resource for which the utilization is used to trigger an adjustment.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.NetworkUtilizationTrigger.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersPointInTimeTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersPointInTimeTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersPointInTimeTrigger">PointInTimeTrigger</a></a></h2>

<p>A PointInTimeTrigger is a trigger that is defined by the time on which a spd.TargetGroup should be adjusted.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersScalingTrigger">ScalingTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersPointInTimeTrigger.pointInTime" class="teletype">pointInTime</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td><p>The simulation time at which the target group should be adjusted.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.PointInTimeTrigger.attr"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger">ProcessingResourceUtilizationBasedTrigger</a></a></h2>

<p>An abstract class for triggers based on the utilization of a processing resource such as CPU, RAM or HDD.</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersResourceUtilizationBasedTrigger">ResourceUtilizationBasedTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger.resourceContainer" class="teletype">resourceContainer</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"></span></div>
<div class="label">Cardinality: [0..*]</div>
</td> 
<td> <p>A list of resource containers for which the processing resource utilization is collected. If left empty, all resource containers as referenced by the TargetGroup are used.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.ProcessingResourceUtilizationBasedTrigger.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersRAMUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersRAMUtilizationTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersRAMUtilizationTrigger">RAMUtilizationTrigger</a></a></h2>

<p>A utilization based trigger based on the RAM resource.</p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersProcessingResourceUtilizationBasedTrigger">ProcessingResourceUtilizationBasedTrigger</a></h4><h2 id="deunistuttgartsqaslingshotspdtriggersResourceUtilizationBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersResourceUtilizationBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersResourceUtilizationBasedTrigger">ResourceUtilizationBasedTrigger</a></a></h2>

<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger">ThresholdBasedTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersResourceUtilizationBasedTrigger.processingResourceAggregation" class="teletype">processingResourceAggregation</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersAGGREGATIONMETHOD">AGGREGATIONMETHOD</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td><p>The aggregation for monitors inside a single resource container. Since a resource container may consists of multiple resources of same type (e.g., several CPUs) then the specified aggregation method determines how multiple monitors should be aggregated within a single resource container.</p>
</td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersResourceUtilizationBasedTrigger.resourceContainerAggregation" class="teletype">resourceContainerAggregation</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersAGGREGATIONMETHOD">AGGREGATIONMETHOD</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td><p>The aggregation accross different resource containers in the Target Group. For example if two containers C1 and C2 have a resource utilizaiton of 0.6, respectively 0.8, then choosing AVERAGE as an aggreagtion method then it determines that the value of 0.7 should be compared against the threshold value. </p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.ResourceUtilizationBasedTrigger.attr"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersResponseTimeTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersResponseTimeTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersResponseTimeTrigger">ResponseTimeTrigger</a></a></h2>

<p>The ResponseTimeTrigger is a TimeBasedTrigger that is based on the response time exceeding a reference threshold value. </p>
<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersTimeBasedTrigger">TimeBasedTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersResponseTimeTrigger.operationSignature" class="teletype">operationSignature</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"></span></div>
<div class="label">Cardinality: [0..*]</div>
</td> 
<td> <p>The operation from which the response time is used. </p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.ResponseTimeTrigger.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersScalingTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersScalingTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersScalingTrigger">ScalingTrigger</a></a></h2>

<p>ScalingTrigger encapsulates both what is observed on the modeled system (the monitoring) as well as how such observation lead to a trigger (the analysis part). 
For example, a CPUThresholdBasedTrigger (a possible implementation of this class) defines both how CPU is going to be monitored from the TargetGroup as well as that it is a simple threshold based trigger.</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h2 id="deunistuttgartsqaslingshotspdtriggersTHRESHOLDDIRECTION"><a href="#deunistuttgartsqaslingshotspdtriggersTHRESHOLDDIRECTION"><a href="#deunistuttgartsqaslingshotspdtriggersTHRESHOLDDIRECTION">THRESHOLDDIRECTION</a></a></h2>

<p>The threshold direction can be either EXCEEDED or UNDERCUT.</p>
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
		<span class="teletype">EXCEDEED</span>
	</td>
	<td>
		0
	</td>
	<td>
	</td>	
</tr>
<tr>
	<td>
		<span class="teletype">UNDERCUT</span>
	</td>
	<td>
		1
	</td>
	<td>
	</td>	
</tr>
</table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.THRESHOLDDIRECTION.lit"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersTaskCountTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersTaskCountTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersTaskCountTrigger">TaskCountTrigger</a></a></h2>

<h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger">ThresholdBasedTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersTaskCountTrigger.processingResourceAggregation" class="teletype">processingResourceAggregation</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersAGGREGATIONMETHOD">AGGREGATIONMETHOD</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td><p>The aggregation for monitors inside a single resource container. Since a resource container may consists of multiple resources of same type (e.g., several CPUs) then the specified aggregation method determines how multiple monitors should be aggregated within a single resource container.</p>
</td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersTaskCountTrigger.resourceContainerAggregation" class="teletype">resourceContainerAggregation</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersAGGREGATIONMETHOD">AGGREGATIONMETHOD</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td><p>The aggregation accross different resource containers in the Target Group. For example if two containers C1 and C2 have a resource utilizaiton of 0.6, respectively 0.8, then choosing AVERAGE as an aggreagtion method then it determines that the value of 0.7 should be compared against the threshold value. </p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.TaskCountTrigger.attr"></a>
<table>
<tr>
	<th colspan="3"><div class="tableHeader">References</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersTaskCountTrigger.resourceContainer" class="teletype">resourceContainer</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"></span></div>
<div class="label">Cardinality: [0..*]</div>
</td> 
<td> <p>A list of resource containers for which task count is used. If left empty, all resource containers as referenced by the TargetGroup are used.</p>
</td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.TaskCountTrigger.ref"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger">ThresholdBasedTrigger</a></a></h2>

<p>A ThresholdBasedTrigger is the supertype of triggers that for analysis has a simple threshold check for breach or undercut. </p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersScalingTrigger">ScalingTrigger</a></h4><table>
<tr>
	<th colspan="3"><div class="tableHeader">Attributes</div></th>
</tr>
<tr>
	<th><div class="columnHeader">Name</div></th>
	<th><div class="columnHeader">Properties</div></th>
	<th><div class="columnHeader">Documentation</div></th>
</tr>
<tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger.threshold" class="teletype">threshold</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
<div class="keyValue"><span class="label">Default: </span><span class="teletype">0.0</span></div>
 </td> <td></td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger.thresholdDirection" class="teletype">thresholdDirection</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype"><a href="#deunistuttgartsqaslingshotspdtriggersTHRESHOLDDIRECTION">THRESHOLDDIRECTION</a></span></div>
<div class="label">Cardinality: [0..1]</div>
 </td> <td></td>
		</tr><tr>	<td><div id="deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger.violationWindow" class="teletype">violationWindow</div>
	</td>
	<td><div class="keyValue"><span class="label">T: </span><span class="teletype">EDouble</span></div>
<div class="label">Cardinality: [1..1]</div>
 </td> <td></td>
		</tr></table>
<a href="#de.unistuttgart.sqa.slingshot.spd.triggers.ThresholdBasedTrigger.attr"></a>
<h2 id="deunistuttgartsqaslingshotspdtriggersTimeBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersTimeBasedTrigger"><a href="#deunistuttgartsqaslingshotspdtriggersTimeBasedTrigger">TimeBasedTrigger</a></a></h2>

<p>A superclass of thershold based triggers that base the trigger on time units such as Response Time or waiting time etc.</p>
<div class="eclassProps">EClass properties:<div class="eclassPropList"><span class="label">Abstract</span></div></div><h4><b>Supertype:</b><a href="#deunistuttgartsqaslingshotspdtriggersThresholdBasedTrigger">ThresholdBasedTrigger</a></h4></body>
</html>
