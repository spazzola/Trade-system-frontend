<template>
     <div class="footer">
        <div id="footer"> &copy; 2020 Forest Industry S.A. All rights reserved.
            <router-link to="/login" class="tilelink"> &emsp; Panel administratora</router-link>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
.footer
{
    position: relative;
    width: 100%;
    height: 30px;
}

#footer
{
    position: absolute;
    bottom: -910px;
    height: 30px;
    width: 100%;
    font-size: 0.70vw;
    font-family: 'Libre Baskerville', serif;
    text-align: center;
    color: #ffffff;
}

a.tilelink
{
    color: #ffffff;
    text-decoration: none;
}
</style>