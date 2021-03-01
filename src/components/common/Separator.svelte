

<div>
    <span>o</span>
</div>

<style>
    div{
        display:grid;
        position:relative;
        width: 16rem;
        height: 16px;
        text-align: center;
    }
    span::before{
        content:'';
        box-shadow: 0 0 1px .5px #6c757d;
        display:block;
        width:7rem;
        transform: rotate(0deg) translateY(10px);
        position:absolute;
    
    }
    span::after{
        content:'';
        display:block;
        width:7rem;
        box-shadow: 0 0 1px .5px #6c757d;
        transform: rotate(0deg) translateY(-9px);
        position:absolute;
        right: 0;
        
    }
</style>