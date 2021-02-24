<script>
    import {Link} from 'svelte-routing';
    export let to= '', message= 'no-data', background= '', color= '#fff';
</script>

<div style={`background: ${background}`}>

    <Link {to} style={`color: ${color}`}>
        <span>
            {message}
        </span>
    </Link>

</div>

<style>
    div{
        display: flex;
        justify-content: center;
        align-items: center;
        cursor:pointer;
        text-align: center;
        width: 7rem;
        height: 2.5rem;
        font-weight:500;
        font-size: 1em;
        padding: .8rem 0 .8rem 0;
        border-radius: .3rem;
        text-shadow: 0 1px 0 rgba(255,255,255,.3);
    }
    div:hover{
        
        filter:brightness(.9)
    }
    @media screen and (min-width: 768px){
        div{
            width: 9rem;
        }
    }
    
    
</style>