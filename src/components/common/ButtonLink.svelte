<script>
    import {Link} from 'svelte-routing';

    export let to= '', message= 'no-data', background= '', color= '#fff', svg= '';
    
</script>

<!-- <div style={`background: ${background}`}> -->
    
    <Link {to} style={`color: ${color}`} >
        <div style={`background: ${background}`}>

            <i class={svg}></i>

            <span>{message}</span>

        </div>
    </Link>

<!-- </div> -->

<style>
    span{
        display:none;
    }
    div{
        display: flex;
        justify-content: center;
        align-items: center;
        cursor:pointer;
        text-align: center;
        padding: 1rem 2rem;
        /* font-weight:500; */
        /* font-size: 1em; */
        
        border-radius: .3rem;
    }
    div:hover{
        
        filter:brightness(.9);
    }
    i{
        color: #fff;
    }
    @media screen and (min-width: 768px){
        span{
            display:inline-block;
        }
        div{
            padding: 16px 8px 16px 8px;
        }
    }
    
    
</style>