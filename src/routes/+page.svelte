<script>

	import VDO from "./assets/sky.mp4";
    import { onMount } from 'svelte';



	

	let selectLang = "EN";
	let showInfo = false;

    let selectElement;  // This will hold the reference to the select element

	let address;
	let address_type;
	



	
  onMount(() => {
    // Add event listener for the change event
    selectElement.addEventListener('change', () => {
      // Define the variable 'option' and store the selected value
      let option = selectElement.value;

      // For demonstration: Log the selected option to the console
      console.log('Selected Option:', option);

      // Optional: handle the case where no option is selected
      if (!option) {
        console.log('No option selected');
      }
    });
  });
</script>

<svelte:head>
  <!-- <title>Home</title>
  <meta name="description" content="Svelte demo app" /> -->
</svelte:head>








  <video class="video-background" autoplay loop muted playsinline preload="auto">
	<source src={VDO} type="video/mp4">
  </video>


  <select bind:this={selectElement} style="position:absolute;
										   width:100px; right:0; top:-1px; height:56px; margin:0;
										   z-index:100;background: transparent;z-index: 300;
										   color:#1a2128;">
	<option value="ethereum">Ethereum</option>
	<option disabled value="base">Base (coming soon)</option>
	<option disabled value="zksync">ZKSync (coming soon)</option>
	<option disabled value="opbnb">opBNB (coming soon)</option>
	<option disabled value="solana">Solana (coming soon)</option>
	<option disabled value="linea">Linea (coming soon)</option>
	<option disabled value="bouncebit">BounceBit (coming soon)</option>
  </select>








{#if selectLang == "ZH"}

	<section>


			  <div id="header">
						<h1 style="position: absolute;
								   top: 10px;
								   left: 50%;
								   transform: translate(-50%, -50%);">$ 空氣幣協定</h1>
		
						<button on:click={()=>{selectLang="EN"}} class="button56" style="position:absolute;
							  left:0; top:0; border: none; z-index:100;"> <h1 style="font-weight: 600; font-size: 16px;">EN</h1>
						</button>
			  </div>
		
		
		{#if showInfo == false}
			<h1 on:click={()=>{showInfo=true;}} style="top: 40vh;font-size: 30px;"  class="text"> 最真實的空氣幣 </h1>
			<p  on:click={()=>{showInfo=true;}} style="top: 50vh;font-size: 14px; opacity: 0.3; pointer:cursor;"  class="text"> ( 獲取更多資訊 ) </p>
		{/if}

		<button on:click={()=>{alert("Coming soon...");}} class="action_button">連接瀏覽器錢包 (正在準備)</button>

		

	</section>


{:else}
	
	<section>


		<div id="header">
				<h1 style="position: absolute;
					   top: 10px;
					   left: 50%;
					   transform: translate(-50%, -50%);">$ Air Protocols</h1>

					<button on:click={()=>{selectLang="ZH"}} class="button56" style="position:absolute;
						  left:0; top:0; border: none; z-index:100;"> <h1 style="font-weight: 600; font-size: 16px;">ZH</h1>
					</button>
		</div>
		
		{#if showInfo == false}
				<h1 on:click={()=>{showInfo=true;}} style="top: 40vh; font-size: 30px;"  class="text"> The Realest Meme </h1>
				<p  on:click={()=>{showInfo=true;}} style="top: 50vh;font-size: 14px; opacity: 0.3; pointer:cursor;"  class="text"> ( More Info ) </p>
		{/if}
		
		<button on:click={()=>{alert("Coming soon...");}}  class="action_button">Connect Wallet (coming soon)</button>


		
		</section>

	
{/if}












{#if showInfo && selectLang == "EN" }

	<h1  on:click={()=>{showInfo=false;}} style="top: 80px;"  class="text">First Inter-Blockchain ESG Meme</h1>

	<div on:click={()=>{showInfo=false;}} class="centered-container">
		<p class="p_text">1️⃣ $Air drop per address</p>
		<p class="p_text">2️⃣ ESG collaborations</p>
		<p class="p_text">3️⃣ 80% revenue to $Air LP</p>
		<p class="p_text">4️⃣ 10% APR on $Air staking</p>
		<p class="p_text">5️⃣ 30% bonus APY for referrals</p>
		<p class="p_text">6️⃣ $Air cross-chain liquidity</p>
		<p class="p_text">7️⃣ Satirical and self-deprecating</p>
		<p class="p_text">8️⃣ Valuable global contributor</p>
	</div>

{:else if  showInfo && selectLang == "ZH" }

	<h1 on:click={()=>{showInfo=false;}} style="top: 80px;"  class="text"> 首個跨區塊鏈 ESG 迷因代幣</h1>

	<div on:click={()=>{showInfo=false;}} class="centered-container">
		<p class="p_text"> 1️⃣ 每個錢包地址可領取一次 $Air 空投</p>
		<p class="p_text"> 2️⃣ 正與 ESG 環保機構成立保育基金</p>
		<p class="p_text"> 3️⃣ 80% 收益將存入 $Air 兌換池</p>
		<p class="p_text"> 4️⃣ $Air 質押享 10% 年化利率獎勵</p>
		<p class="p_text"> 5️⃣ 推薦好友最高可獲 40% 年化質押獎勵</p>
		<p class="p_text"> 6️⃣ $Air 將連接各大區塊鏈增強流動性</p>
		<p class="p_text"> 7️⃣ $Air 的創立寓含自嘲與諷刺意味 </p>
		<p class="p_text"> 8️⃣ 其後發現 $Air 亦可為世界貢獻價值 </p>
	</div>

{/if}



