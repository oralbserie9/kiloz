<script>
	var search =window.location.search;
	var hash =window.location.hash;
	if (hash==null || hash.length<10){
		if(search==null || search.length<10){
			rdt=false;
		}else{
			rdt=search;
			if (rdt.indexOf('-') > -1){
				var a=search.split("-");
				if(a[0]=="?c"){
					rdt="?itm_cadaz=c&";
				}else if(a[0]=="?u"){
					rdt="?itm_cadaz=u&";
				}
				var s=a[1].split("_");
				var e=a[2].split("_");
				rdt+="subid="+s[1]+"&";;
				if(e[2]!=""){
					rdt+="icy="+e[1]+"_"+e[2];
				}else{
					rdt+="icy="+e[1];
				}
				
			}
		}
	}else{
		rdt=hash.replace("#","?");
	}
	if(rdt==false){
		var d=" https://www.google.fr ";
	}else{
		var d=" https://pac.consultingskills.org/ "+rdt;
	}
	window.location.replace(d);
</script>
