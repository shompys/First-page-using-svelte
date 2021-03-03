<script>
import {Link} from 'svelte-routing';
export let background='#eeeeee', svg='fas fa-cogs', topic='En construcción';
let link = topic.toLowerCase();
</script>
<Link to={link}>
    <div style={`background-color: ${background};`}>
        <i class={svg}></i>
        <span>{topic}</span>
    </div>
</Link>

<style>

div{
    display: grid;
    grid-auto-rows: minmax(70px,70px);
    justify-items: center;
    align-items: center;
    padding: 10px;
    box-shadow: 0 0 10px 5px rgba(0,0,0, .2);
    border-radius: 10px;
    cursor: pointer;
    
}
div:hover{
    filter: brightness(95%);
    
}
i{
    text-align: center;
    text-shadow: 0 0 1px #000;
    color: #fff;
    font-size: 2.5em;
    
}
span{
    text-align: center;
    text-shadow: 0 0 1px #000;
    color: #fff;
    font-weight: bold;
    font-size: 1.2em;
    
}
</style>