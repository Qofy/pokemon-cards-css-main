<script>
  import { onMount } from "svelte";
	import CardList from "../../Cards.svelte";
	import Card from "../../lib/components/CardProxy.svelte";

	// let query = "";
	let isLoading = true;

	let showcase;
	let basics;
	let reverse;
	let holos;
	let cosmos;
	let amazings;
	let radiant;
	let basicGallery;
	let vee;
	let veeUltra;
	let veeAlt;
	let veeMax;
	let veeMaxAlt;
	let veeStar;
	let trainerHolo;
	let rainbow;
	let gold;
	let veeGallery;
	let shinyVault;

	const getCards = async () => {
		let promiseArray = [];
		let cardFetch = await fetch("/data/cards.json");
		let cards = await cardFetch.json();
		return cards;
	};

	const loadCards = async() => {
		return getCards()
			.then((cards) => {
				window.cards = cards;
				showcase = cards[0];
				basics = cards.slice(1, 4);
				reverse = [...cards.slice(4, 7), ...cards.slice(70,76)];
				holos = cards.slice(7, 13);
				cosmos = cards.slice(13, 16);
				amazings = cards.slice(76, 85);
				radiant = cards.slice(16, 19);
				basicGallery = cards.slice(19, 22);
				vee = cards.slice(22, 25);
				veeUltra = cards.slice(25, 28);
				veeAlt = cards.slice(28, 34);
				veeMax = cards.slice(37, 40);
				veeMaxAlt = cards.slice(40, 43);
				veeStar = cards.slice(43, 46);
				trainerHolo = cards.slice(46, 52);
				rainbow = cards.slice(52, 58);
				gold = cards.slice(58, 64);
				veeGallery = cards.slice(64, 70);
				shinyVault = cards.slice(85,91);
				isLoading = false;
			});
	};

	onMount(() => {
		loadCards();
		const $headings = document.querySelectorAll("h1,h2,h3");
		const $anchor = [...$headings].filter((el) => {
			const id = el.getAttribute("id")?.replace(/^.*?-/g,"");
			const hash = window.location.hash?.replace(/^.*?-/g,"")
			return id === hash;
		})[0];
		if( $anchor ) {
			setTimeout(() => {
				$anchor.scrollIntoView();
			},100);
		}
	});

</script>

<main>
  <div class="head">
    <h1>
      Portfolio
    </h1>
    <h3>
      We love to produce software that covers a need.
    </h3>
  </div>

  <div class="content">
    <div>
      <CardList>
			{#if isLoading}
				loading...
			{:else}
				{#each veeAlt as card, index}
					<Card
						id={card.id}
						name={card.name}
						number={card.number}
						set={card.set}
						types={card.types}
						supertype={card.supertype}
						subtypes={card.subtypes}
						rarity={card.rarity}
					/>
				{/each}
			{/if}
		</CardList>
    </div>
    <div>
      <CardList>
			{#if isLoading}
				loading...
			{:else}
				{#each trainerHolo as card, index}
					<Card
						id={card.id}
						name={card.name}
						number={card.number}
						set={card.set}
						types={card.types}
						supertype={card.supertype}
						subtypes={card.subtypes}
						rarity={card.rarity}
					/>
				{/each}
			{/if}
		</CardList>

    </div>
    <div>
      <CardList>
			{#if isLoading}
				loading...
			{:else}
				{#each rainbow as card, index}
					<Card
						id={card.id}
						name={card.name}
						number={card.number}
						set={card.set}
						types={card.types}
						supertype={card.supertype}
						subtypes={card.subtypes}
						rarity={card.rarity}
					/>
				{/each}
			{/if}
		</CardList>
    </div>

    <div>
      <CardList>
			{#if isLoading}
				loading...
			{:else}
				{#each gold as card, index}
					<Card
						id={card.id}
						name={card.name}
						number={card.number}
						set={card.set}
						types={card.types}
						supertype={card.supertype}
						subtypes={card.subtypes}
						rarity={card.rarity}
					/>
				{/each}
			{/if}
      
		</CardList>
    </div>
    
  </div>
</main>

<style>
  h1{
    font-size: 3rem;
    font-weight: 700;
  }
  h3{
    font-size: 2rem;
  }
	main{
		background-color: #171717;
		height: 100%;
		box-shadow: 0 4px 24px 0 #a0bd35, 0 1.5px 6px 0 #87a909;
	}
  .head{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .content{
    display: grid;
    grid-template-columns: repeat(2,1fr);
  }
</style>