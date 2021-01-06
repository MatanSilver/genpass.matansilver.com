<script>
	let dictionary = '1234567890-=qwertyuiop[]asdfghjkl;zxcvbnm,./!@#$%^&*()_+QWERTYUIOP{}|ASDFGHJKL:ZXCVBNM<>?'.split('')
	Array.prototype.sample = function(){
		return this[Math.floor(Math.random()*this.length)];
	}
	Array.prototype.samples = function(n){
		let newArray = []
		for (let i = 0; i < n; i++) {
			newArray.push(this.sample())
		}
		return newArray.join('')
	}
	let pass = dictionary.samples(16)
	function handleClick() {
		pass = dictionary.samples(16)
	}
</script>

<main>
	<h1>Generate Strong Passwords</h1>
	<p>Passwords are generated on your computer, not the server. I can't see it.</p>
	<button on:click={handleClick}>
		New Password
	</button>
	<p>{pass}</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>