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
        width: 9rem;
        height: 2.5rem;
        font-weight:500;
        font-size: 1em;
        padding: .8rem 0 .8rem 0;
        border-radius: .3rem;
    }
    div:hover{
        filter:brightness(.9)
    }
</style>