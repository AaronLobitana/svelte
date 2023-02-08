<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/brimreaper.jpg';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>


<section>
<div class="topbuttons">
	<button class="dupe">Duplicate</button>
	<button class="changebg">Change Background</button>
	<button class="changehg">Change Heading</button>
	<button class="del" id="del">Delete</button>
	</div>
	
	<div class="overallcard">
	  <div class="box">
		
		<img class="pic" src="https://pbs.twimg.com/media/FajpQj_XwAEwCWw.jpg">
		
		<div class="heading">
		  <h1>the brim reaper</h1>
		</div>
		
		<div class="details">
		  <h3>fear the reaper</h3>
		</div>
		<div class="reveal">
		  <button class="detailsbutton">Details</button>
		</div>
	 
	 </div>
	  
	</div>


	<script>
		document.querySelector('.dupe').addEventListener('click', function(e) {
  const copy = document.querySelector('.overallcard').cloneNode(true);
  document.body.appendChild(copy);
});

function togglePar()
{
  const myparagraphs = document.querySelectorAll('.details');
  for (var i = 0; i < myparagraphs.length; i++)
  {
    if (myparagraphs[i].style.display ==  "none")
    {
      myparagraphs[i].style.display = "block";
    }
    else
    {
      myparagraphs[i].style.display = "none";
    }
    
  }
}
document.querySelector('.detailsbutton').addEventListener("click", togglePar);


function changeHg()
{
  const myheading = document.querySelectorAll('.heading h1');
  var name = "something else";
  for (var i = 0; i < myheading.length; i++)
  {
    myheading[i].innerHTML = name;
  }

}

document.querySelector(".changehg").addEventListener("click", changeHg);

function changeBg()
{
  const mybackground = document.querySelectorAll('.box');
  for (var i = 0; i < mybackground.length; i++)
  {
    if (mybackground[i].style.backgroundColor === "white")
    {
      mybackground[i].style.backgroundColor = "#B19CD9";
    }
    else
    {
      mybackground[i].style.backgroundColor = "white";
    }
  }
}

document.querySelector(".changebg").addEventListener("click", changeBg);

document.querySelector('#del').addEventListener('click', function(e) {
    if (document.querySelector('.overallcard:last-child') !== document.querySelector('.overallcard')) 
    {
      document.querySelector('.overallcard:last-child').remove();      
    }
  
});
	</script>
</section>


<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}


	.overallcard{
  width: 400px;
  border: 4px solid black;
  display: inline-flex;
}

.box{
  background-color: #B19CD9;
}

.pic{
  width: 400px;
  transition: transform .5s ease-in-out;
}

.pic:hover{
  transform: rotate(360deg);
}

.heading{
  text-align: center;
}

.details{
  text-align: center;
  display: none;
}

.topbuttons{
  margin: 10px 0px 10px 0px;
  display: block;
}


.dupe{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.changebg{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.changehg{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.del{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.detailsbutton{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
  margin: 10px;
}

.detailsbutton:hover{
  background-color: black;
}

.detailsbutton:focus{
  background: gray;
  color: #041E42;
}

.reveal{
  text-align: center;
}


.dupe:hover{
  background-color: black;
}

.dupe:focus{
  background: gray;
  color: #041E42;
}

.changebg:hover{
  background-color: black;
}

.changebg:focus{
  background: gray;
  color: #041E42;
}

.changehg:hover{
  background-color: black;
}

.changehg:focus{
  background: gray;
  color: #041E42;
}

.del:hover{
  background-color: black;
}

.del:focus{
  background: gray;
  color: #041E42;
}

@media only screen and (max-width: 425px)
{
  .reveal{
    display: none;
  }

  .overallcard{
    width: 250px;
    border: 4px solid black;
    display: inline-flex;
  }
  
  .pic{
    width: 250px;
    transition: transform .5s ease-in-out;
  }
}

</style>
