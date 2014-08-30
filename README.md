hellomobile
===========

My first repository in github.
/*
*
window.$ = window.jQuery = WLJQ;
var busyIndicator = null;
function wlCommonInit(){

	 WL.Logger.debug("inside the wlcommoninit");
	 busyIndicator=new WL.BusyIndicator('AppBody');
	 busyIndicator= new WL.BusyIndicator('AppBody1');
	 // getData();
}

$("#exit").bind('click',function logout(){
	
	WL.Client.logout('LDAPRealm', {onSuccess: function (){
		 WL.Client.reloadApp();
	}});
});


function getData(){
	var invocationData={
			adapter:'clientadapter',
			procedure:'GetClients'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:loadFeedsSuccess,
	onFailure:loadFeedsFailure,
});

}

function loadFeedsSuccess(result)
{
	
	WL.Logger.debug("Feed retrieve success"+JSON.stringify(result));
	$("#result").html(result.invocationResult.resultSet[0].Client_F_name);
	$("#result1").html(result.invocationResult.resultSet[0].Client_Address);
	$("#result2").html(result.invocationResult.resultSet[0].Appointment_time);
		}

function loadFeedsFailure(result){
	WL.Logger.error("Feed retrieve failure");
}


/*function getData1(){
	var invocationData={
			adapter:'Appointment',
			procedure:'Appointments'
	};

WL.Client.invokeProcedure(invocationData,{
	onsuccess:getFeedsSuccess,
	onFailure:getFeedsFailure,
});

}*/

$("#upcomingid").click(function(){
	
	var invocationData={
			adapter:'clientadapter',
			procedure:'procedure2'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess,
	onFailure:getFeedsFailure,
});


});


function getFeedsSuccess(result)
{
	
	
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		tmp=tmp+"<li data-icon='false'><a href='#'><h2>"+res.resultSet[i].Client_F_name+"</h2><p>Address: "+res.resultSet[i].Client_Address+"</p><p>Appointment Date :"+res.resultSet[i].Appointment_1_Date+"</p></a></li>"; 
	}
	
	$("#temp8").html(tmp);
	$.mobile.changePage($("#upcomingpages"),{transition:"flip"},true,true);
	$("#temp8").listview("refresh");
		}

function getFeedsFailure(result){
	WL.Logger.error("Feed retrieve failure");
}

$("#cc").click(function(){
	
	var invocationData={
			adapter:'Appointment',
			procedure:'procedure2'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess121,
	onFailure:getFeedsFailure121,
});


});


function getFeedsSuccess121(result)
{
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		
		tmp=tmp+"<li>"+res.resultSet[i].Client_F_name+"</li>";
		
	}
	
	$("#confid").html(tmp);
	$.mobile.changePage($("#checklistpages"),{transition:"flip"},true,true);
	$("#confid").listview("refresh");
		}

function getFeedsFailure121(result){
	WL.Logger.error("Feed retrieve failure");
}

$("#pc").click(function(){
	
	var invocationData={
			adapter:'Appointment',
			procedure:'procedure3'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess122,
	onFailure:getFeedsFailure122,
});


});


function getFeedsSuccess122(result)
{
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		
		tmp=tmp+"<li>"+res.resultSet[i].Client_F_name+"</li>";
		
	}
	
	$("#potid").html(tmp);
	$.mobile.changePage($("#checklistpages"),{transition:"flip"},true,true);
	$("#potid").listview("refresh");
		}

function getFeedsFailure122(result){
	WL.Logger.error("Feed retrieve failure");
}

$("#rc").click(function(){
	
	var invocationData={
			adapter:'Appointment',
			procedure:'procedure4'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess123,
	onFailure:getFeedsFailure123,
});


});


function getFeedsSuccess123(result)
{
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		
		tmp=tmp+"<li>"+res.resultSet[i].Client_F_name+"</li>";
		
	}
	
	$("#rejid").html(tmp);
	$.mobile.changePage($("#checklistpages"),{transition:"flip"},true,true);
	$("#rejid").listview("refresh");
		}

function getFeedsFailure123(result){
	WL.Logger.error("Feed retrieve failure");
}
$("#appointmentId").click(function(){
	
	var invocationData={
			adapter:'clientadapter',
			procedure:'GetClients'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess1,
	onFailure:getFeedsFailure1,
});


});


function getFeedsSuccess1(result)
{
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		
		tmp=tmp+"<li data-icon='false'><h2>"+res.resultSet[i].Client_F_name+"</h2><p>Address:"+res.resultSet[i].Client_Address+"</p><p>Appointment Time:"+res.resultSet[i].Appointment_time+"</p></li>";
		
	}
	
	$("#temp10").html(tmp);
	$.mobile.changePage($("#appointmentPages"),{transition:"flip"},true,true);
	$("#temp10").listview("refresh");
		}

function getFeedsFailure1(result){
	WL.Logger.error("Feed retrieve failure");
}

$("#missedid").click(function(){
	
	var invocationData={
			adapter:'clientadapter',
			procedure:'procedure3'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess4,
	onFailure:getFeedsFailure4,
});


});

$("#upcomingmissed").click(function(){
	
	var invocationData={
			adapter:'clientadapter',
			procedure:'procedure3'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess4,
	onFailure:getFeedsFailure4,
});


});


function getFeedsSuccess4(result)
{
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		
		tmp=tmp+"<li data-icon='false'><h2>"+res.resultSet[i].Client_F_name+"</h2><p>Address:"+res.resultSet[i].Client_Address+"</p><p>Appointment Time:"+res.resultSet[i].Appointment_time+"</p></li>";
		
	}
	
	$("#misid").html(tmp);
	$.mobile.changePage($("#missedpages"),{transition:"flip"},true,true);
	$("#misid").listview("refresh");
		}

function getFeedsFailure4(result){
	WL.Logger.error("Feed retrieve failure");
}



$("#orderid").click(function(){
	
	var invocationData={
			adapter:'paymentmode',
			procedure:'GetPayment'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess2,
	onFailure:getFeedsFailure2,
});


});


function getFeedsSuccess2(result)
{
	
	
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		tmp=tmp+"<td>"+res.resultSet[i].Client_id+"</td><td>"+res.resultSet[i].Client_name+"</td><td>"+res.resultSet[i].Product+"</td><td>"+res.resultSet[i].Qty+"</td><td>"+res.resultSet[i].Discount+"</td><td>"+res.resultSet[i].TotalCost+"</td>"; 
	}
	
	$("#tdid").html(tmp);
	$.mobile.changePage($("#orderpages"),{transition:"flip"},true,true);
	$("#tdid").listview("refresh");
		}

function getFeedsFailure2(result){
	WL.Logger.error("Feed retrieve failure");
}

$("#receiptid").click(function(){
	
	var invocationData={
			adapter:'reciept',
			procedure:'GetReciept'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess3,
	onFailure:getFeedsFailure3,
});


});


function getFeedsSuccess3(result)
{
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		tmp=tmp+"<td>"+res.resultSet[i].Reciept_Number+"</td><td>"+res.resultSet[i].Client_ID+"</td><td>"+res.resultSet[i].Client_F_name+"</td><td>"+res.resultSet[i].Client_ADDRESS+"</td><td>"+res.resultSet[i].Product+"</td><td>"+res.resultSet[i].Quantity+"</td><td>"+res.resultSet[i].Total+"</td>"; 
	}
	
	$("#rid").html(tmp);
	$.mobile.changePage($("#receiptpages"),{transition:"flip"},true,true);
	$("#rid").listview("refresh");
		}

function getFeedsFailure3(result){
	WL.Logger.error("Feed retrieve failure");
}


$("#paymentid").click(function(){
	
	var invocationData={
			adapter:'paymentmode',
			procedure:'GetPayment'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess25,
	onFailure:getFeedsFailure25,
});


});


function getFeedsSuccess25(result)
{
	
	
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		tmp=tmp+"<td>"+res.resultSet[i].Client_id+"</td><td>"+res.resultSet[i].Client_name+"</td><td>"+res.resultSet[i].Product_id+"</td><td>"+res.resultSet[i].Qty+"</td><td>"+res.resultSet[i].Discount+"</td><td>"+res.resultSet[i].TotalCost+"</td><td>"+res.resultSet[i].Cheque+"</td><td>"+res.resultSet[i].DD+"</td><td>"+res.resultSet[i].Cash+"</td>"; 
	}
	
	$("#cr2").html(tmp);
	$.mobile.changePage($("#paymentpage"),{transition:"flip"},true,true);
	$("#cr2").listview("refresh");
		}

function getFeedsFailure25(result){
	WL.Logger.error("Feed retrieve failure");
}


$("#historyid").click(function(){
	
	var invocationData={
			adapter:'History',
			procedure:'GetHistory'
	};

WL.Client.invokeProcedure(invocationData,{
	onSuccess:getFeedsSuccess15,
	onFailure:getFeedsFailure15,
});


});


function getFeedsSuccess15(result)
{
	
	
	
	var res=result.invocationResult;
	var tmp='';
	for(var i=0;i<result.invocationResult.resultSet.length;i++){
		tmp=tmp+"<tr><td>"+res.resultSet[i].Client_id+"</td><td>"+res.resultSet[i].Client_name+"</td><td>"+res.resultSet[i].Product+"</td><td>"+res.resultSet[i].Appointment_Date+"</td><td>"+res.resultSet[i].Feedback+"</td></tr>"; 
	}
	
	$("#history-table tbody").html(tmp);
	$.mobile.changePage($("#historypage"),{transition:"flip"},true,true);
	$("#history-table tbody").listview("refresh");
		}

function getFeedsFailure15(result){
	WL.Logger.error("Feed retrieve failure");
}




$("#appointmentback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});

$("#upcomingback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});

$("#missedback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});

$("#orderback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});

$("#productback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});


$("#receiptback").click(function(){
	
	$.mobile.changePage($("#orderpages"));
});

$("#harddiskback").click(function(){
	$.mobile.changePage($("#productspages"));
});


$("#performanceindexback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});


$("#specialoffersback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});


$("#checklistback").click(function(){
	
	$.mobile.changePage($("#hellomobilepages"));
});


$("#appointmentId").click(function(){
	
	$.mobile.changePage($("#appointmentPages"));
});




$("#missedid").click(function(){
	$.mobile.changePage($("#missedpages"));
});

$("#orderid").click(function(){
	$.mobile.changePage($("#orderpages"));
});

$("#upcomingtoday").click(function(){
	
	$.mobile.changePage($("#appointmentPages"));
});

$("#upcomingmissed").click(function(){
	$.mobile.changePage($("#missedpages"));
});

$("#missedtoday").click(function(){
	
	$.mobile.changePage($("#appointmentPages"));
});

$("#missedupcoming").click(function(){
	$.mobile.changePage($("#upcomingpages"));
});

$("#receiptid").click(function(){
	$.mobile.changePage($("#receiptpages"));
});

$("#productsid").click(function(){
	$.mobile.changePage($("#productspages"));
});

$("#harddisk").click(function(){
	$.mobile.changePage($("#harddiskpages"));
});

$("#checklistid").click(function(){
	$.mobile.changePage($("#checklistpages"));
});

$("#specialoffersid").click(function(){
	$.mobile.changePage($("#specialofferspages"));
});

$("#performanceindexId").click(function(){
	$.mobile.changePage($("#performanceindexpages"));
});


$("#dialogid").click(function(){
	$.mobile.changePage($("#dialogpages"));
});

$("#checklistid").click(function(){
	$.mobile.changePage($("#checklistpages"));
});

$("#harddiskid").click(function(){
	$.mobile.changePage($("#harddiskpages"));
});

$("#paymentid").click(function(){
	$.mobile.changePage($("#paymentpage"));
});

$("#historyid").click(function(){
	$.mobile.changePage($("#historypage"));
});
