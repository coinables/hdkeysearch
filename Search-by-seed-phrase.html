<!DOCTYPE html>
<html>
<head>
<script type="text/javascript" src="buidl.js"></script>
<script type="text/javascript" src="bitcoin.js"></script>
<script type="text/javascript" src="hd.js"></script>
<script src="jquery-3.3.1.min.js"></script>
<link rel = "stylesheet" type = "text/css" href = "style.css" />
</head>
<body>
<h2>Find a key pair within an HD keychain from seed phrase</h2>

Seed Phrase: <input type="text" id="words"><br>
Address to Find/Search: <input type="text" id="addr"><br>
<span title="how many keys deep in the HD chain should be searched?">Depth</span>: <input type="number" id="depth" value="25"><br>


<button id="searchbtn">SEARCH</button>
<br>
<div id="result">Results (this might take a moment)</div>
<script>
//var words = "segment increase inch ensure corn cigar suggest fetch output proof peasant enact";
//var addr = "1c4XzQx7Uh8CnxzAN5CRrUjkbxGB1GUWp";

var searchbtn = document.getElementById("searchbtn");
searchbtn.onclick = function(){

	var words = document.getElementById("words").value;
	var addr = document.getElementById("addr").value;
	var depth = document.getElementById("depth").value;
	inkeychain(addr, words, depth);
}


function inkeychain(addr, keychain, depth){
		var isfound = false;
		for(var i=0;i<depth;i++){
    		var seed = hd.bip39.mnemonicToSeed(keychain);
    		var root = b.bitcoin.HDNode.fromSeedBuffer(seed)
    		//const root = bitcoin.HDNode.fromSeedHex(seed.toString('hex'))
    		var wallet = root.derivePath("m/44'/0'/0'/0/"+i);
    
    		//legacy
    		var address = wallet.getAddress();
    		var wif = wallet.keyPair.toWIF();
			
			//segwit p2sh
			var pubKey = wallet.keyPair.getPublicKeyBuffer();
			var pubKeyHash = b.bitcoin.crypto.hash160(pubKey);
			var redeemScript = b.bitcoin.script.witnessPubKeyHash.output.encode(pubKeyHash);
			var redeemScriptHash = b.bitcoin.crypto.hash160(redeemScript);
			var scriptPubKey2 = b.bitcoin.script.scriptHash.output.encode(redeemScriptHash);
			var p2shsegwit = b.bitcoin.address.fromOutputScript(scriptPubKey2);
    
    		if(address===addr){
			isfound = true;
    			console.log(address, wif);
    			$('#result').html('Found '+addr+' in this keychain at '+i+' position in the keychain');
    			alert('Found!');
    		} else if (p2shsegwit===addr){
				//check for segwit p2sh
				isfound = true; 
				console.log(p2shsegwit, wif);
    			$('#result').html('Found '+addr+' in this keychain at '+i+' position in the keychain');
    			alert('Found!');
			} 
    	}
	if(isfound===false){
		$('#result').html('No matches');
	}
    
}
</script>
</body>
</html>