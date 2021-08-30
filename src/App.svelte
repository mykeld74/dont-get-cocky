<script>
	import './css/reset.css'
	import './css/styles.css'
	const date1 = new Date("07/28/2020");
	const date2 = new Date();
	const timeDiff = Math.abs(date2.getTime() - date1.getTime());
	const diffDays = Math.ceil(timeDiff / 1000 / 60 / 60 / 24);

	let rooster = "./assets/cocky.png";

</script>

<svelte:head>
	<title>Front End Deployment Counter</title>
	<link rel="icon" 
      type="image/png" 
      href="./assets/cocky.png">
</svelte:head>

<main>
	<div class="container">
		<p>It's Been</p>

		<div class="box">
			<p class="numDays">{diffDays}</p> <p class="days">Days</p>
		</div>
		<p>Since our last failed front end deployment!</p>
		<p class="cocky"><img src={rooster} alt="rooster"class="rooster"/>Don't get Cocky!<img src={rooster} alt="rooster"class="rooster reverse"/></p>
	</div>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Encode+Sans+Condensed&family=Rubik+Mono+One&display=swap');
	@keyframes spin {
		from {
			transform: rotateY(0deg);
		}
		to {
			transform: rotateY(360deg);
		}
	}
	@keyframes reverseSpin {
		from {
			transform: rotateY(-180deg);
		}
		to {
			transform: rotateY(180deg);
		}
	}

	.container {
		background: #fff;
		border-radius: 15px;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		font-family: 'Encode Sans Condensed', sans-serif;
		width: 100%;
		max-width: 1200px;
		padding: 2vh 3vw;
		text-align: center;
		margin: 80px auto;
		font-size: clamp(32px, 4vw, 72px);
	}
	.box{
		width: 100%;
		max-width: 500px;
		background: #dedede;
		border-radius: 10px;
		padding: 20px;
	}
	.numDays {
		font-size: clamp(70px, 6vw, 128px);
		font-family: "Rubik Mono One", sans-serif;
		margin: 0;
		padding: 0;
		line-height: 1;
	}
	.days{
		font-size: 80px;
		text-transform: uppercase;
		margin: .25em 0 0 0;
	}
	.cocky{
		color: #990000;
		display: flex;
		align-items: center;
	}
	.rooster{
		width: clamp(32px, 4vw, 72px);
		margin: 0 .5em;
		animation: spin 5s ease-in-out infinite;
	}
	.reverse{
		animation: reverseSpin 5s ease-in-out infinite;
	}
	


</style>