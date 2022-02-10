<script lang="ts">
	let skillz = [
		{name: "C", description: "Basic understanding of C"},
		{name: "Python", description: "Web development using Django / Flask"},
		{name: "Javascript", description: "Front-end development with various frameworks"},
		{name: "HTML", description: "Understanding of how markup works"},
		{name: "CSS", description: "Styling with CSS and/or it's preprocessors"},
		{name: "Vue", description: "The front-end framework"},
		{name: "Svelte", description: "The front end javascript compiler"},
		{name: "Express", description: "The de-facto standard for backend"},
		{name: "Node & npm", description: "The server side javascript framework and the package manager"},
		{name: "Git & Github", description: "Version control and open source"},
		{name: "VSCode", description: "The code editing tool"},
		{name: "Typescript", description: "The javascript superset"},
		{name: "C++", description: "Basics of C++"},
		{name: "Unity & C#", description: "Basic game-dev"},
		{name: "Godot & Gdscript", description: "Basic game-dev using the open source Godot engine"},
		{name: "jQuery", description: "The most popular javascript library"},
		{name: "PostgreSQL", description: "The relational database technology"},
	];
	let query = "";

</script>
<main>
	<div class="first">
		<h1>Portfolio</h1>
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam eius veniam officiis fuga porro ex laudantium, in accusantium perferendis aut beatae itaque quo adipisci possimus voluptate maiores, velit, tempora eveniet!
		</p>
		<div class="centered-h">
			<button class="btn btn-yellow">Hire this guy!</button>
			<button class="btn btn-purple">Contact</button>
		</div>
	</div>
	<div class="spacer layer1"><a href="#search">Scroll down for more<span></span></a></div>
	<div class="second">
		<h1>Skills</h1>
		<div class="centered-v">
			<input id="search" class="search-box" type="search" placeholder="Search..." bind:value={query} />
			<div class="centered-h">
				{#each skillz as skill}
				{#if skill.name.toLowerCase().includes(query.toLowerCase())}
					<div class="card">
						<h3>{skill.name}</h3>
						<hr />
						<p>{skill.description}</p>
					</div>
				{/if}
				{/each}
			</div>
		</div>
	</div>
	<div class="spacer layer2"></div>
	<div class="third">
		<h1>Links</h1>
		<div class="centered-h">
			<div class="display">
				<a href="#search"><h3>Itaglam</h3></a>
			</div>
		</div>
	</div>
</main>

<style lang="scss">
	:global(body), *, main {
		padding: 0;
		margin: 0;
	}

	h1 {
		padding-top: 75px;
		color: #eee;
		font-style: bold;
		font-size: 75px;
		text-align: center;
	}

	p {
		padding: 20px;
		color: #fff;
		text-align: center;
		opacity: 85%;
	}

	.btn {
		border: none;
		outline: none;
		font-style: bold;
		color: #000;
		padding: 13px;
		margin: 0 10px;
		transition: 0.2s;
		border-radius: 4px;
		box-shadow: #111 3px 3px 5px;

		&:hover {
			animation:slidebg 9s linear infinite;
			color: white;
			transform: translateY(3px)
		}
	}

	.btn-yellow {
		background-image: linear-gradient(
			to right,
			#d6d43b,
			#f4f818,
			#d6d43b,
		);
	}

	.btn-purple {
		background-image: linear-gradient(
			to right,
			#a82dce,
			#c418f8,
			#a82dce,
		);
	}

	.first {
		background: #002233;
	}

	.second {
		background: #0066ff;
	}

	.third {
		background: #c76e24;
	}

	.search-box {
		outline: none;
		border: none;
		width: 50%;
		opacity: 80%;
		margin: 15px;
		padding: 15px;
		border-radius: 20px;
		transition: 0.4s;

		&:focus {
			opacity: 90%;
			border-radius: 10px;
		}
	}

	.card {
		background: #002233;
		border-radius: 15px;
		box-shadow: #000 3px 3px 10px;
		transition: 0.4s;

		&:hover {
			transform: translateY(-5px);
		}

		hr {
			opacity: 50%;
		}
	}

	.display {
		background: #13c581;
		border-radius: 30px;
		transition: 0.4s;
		padding: 1vw;

		&:hover {
			transform: translate(-5px, -5px);
		}
	}

	.spacer {
		display: flex;
		justify-content: center;
		align-items: center;
		aspect-ratio: 800/300;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;

		&.layer2 {
			aspect-ratio: 2/1;
		}

		a {
			text-decoration: none;
			color: rgba(255, 255, 255, 0.664);

			span {
				position: absolute;
				top: 70%;
				right: 44%;
				width: 24px;
				height: 24px;
				border-left: 1px solid #fff;
				border-bottom: 1px solid #fff;
				-webkit-transform: rotate(-45deg);
				transform: rotate(-45deg);
				-webkit-animation: sdb04 2s infinite;
				animation: sdb04 2s infinite;
				box-sizing: border-box;
			}
			@-webkit-keyframes sdb04 {
				0% {
					-webkit-transform: rotate(-45deg) translate(0, 0);
				}
				20% {
					-webkit-transform: rotate(-45deg) translate(-10px, 10px);
				}
				40% {
					-webkit-transform: rotate(-45deg) translate(0, 0);
				}
			}
			@keyframes sdb04 {
				0% {
					transform: rotate(-45deg) translate(0, 0);
				}
				20% {
					transform: rotate(-45deg) translate(-10px, 10px);
				}
				40% {
					transform: rotate(-45deg) translate(0, 0);
				}
			}
		}
    }

	@keyframes slidebg {
		to {
			background-position:20vw;
		}
	}

	.layer1 {
        background-image: url("./../assets/wave-haikei.svg");
    }

	.layer2 {
        background-image: url("./../assets/layered-waves-haikei.svg");
    }

	.centered-h {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		justify-items: center;
		flex-wrap: wrap;
		padding: 20px;
		gap: 25px;

		h3, p {
			color: #fff;
			margin: 5px;
		}
	}

	.centered-v {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		justify-items: center;
	}
</style>