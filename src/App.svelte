<script>
  let dates = [
    {date: '4/15', content: 'Learn C++ and Lua, watch a Youtube tutorial on Roblox Studios to get a good grasp.'},
    {date: '4/16', content: 'Learn Java and C# fundamentals. Do some Leetcode with C++. Javascript: Draw out a medium problem and attempt to solve it. Search up js tools if needed.'},
    {date: '4/17', content: 'Touch Ruby basics and fundamentals. Do more Leetcode with C++. Make a simple console game with both Java and C#. Games must be different and must be 40 lines or longer.'},
    {date: '4/18', content: ''},
    {date: '4/19', content: ''},
    {date: '4/20', content: ''},
    {date: '4/21', content: ''},
    {date: '4/22', content: ''},
    {date: '4/23', content: ''},
    {date: '4/24', content: ''},
  ]
  let contentOpen = [{
    "4/15": false, 
    "4/16": false, 
    "4/17": false, 
    "4/18": false, 
    "4/19": false, 
    "4/20": false, 
    "4/21": false, 
    "4/22": false,
    "4/23": false,
    "4/24": false,
  }]
  const open = (x) => () => {
    var date = x.date.date
    contentOpen[0][date] = !contentOpen[0][date]
  }

  const over = (dom) => () => {
    var it = document.getElementById(dom.date.date)
    it.style.opacity = "0.65"
    it.style.cursor = "pointer"
  }

  const out = (dom) => () => {
    var it = document.getElementById(dom.date.date)
    it.style.opacity = "1"
    it.style.cursor = "default"
  }

  function focus(){

  }

  function blur(){

  }
</script>

<main>
  <h1>Svelte Spring Break Schedule</h1>
  {#each dates as date}
  <div class="dateBtn" id={date.date} on:click={open({date})} on:mouseover={over({date})} on:mouseout={out({date})} on:focus={focus} on:blur={blur}>Schedule for {date.date}</div>
    {#each contentOpen as open}
      {#if open[date.date]}
        <div class="content">{date.content}</div>
      {/if}
    {/each}
  {/each}
</main>

<style>
  h1 {
    margin-top: 20px;
    font-weight: bold;
    text-align: center;
    background: -webkit-linear-gradient(red 50%, orange 40%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .dateBtn {
    background-color: lightgray;
    border: 2px solid darkgray;
    text-align: center;
    padding: 4px;
    width: 20%;
    left: 50%;
    transform: translateX(187.5%);
    margin-top: 15px;
    -webkit-touch-callout: none; 
    -webkit-user-select: none; 
    -khtml-user-select: none; 
    -moz-user-select: none; 
    -ms-user-select: none; 
    user-select: none; 
  }

  .content {
    text-align: center;
  }
</style>
