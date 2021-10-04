<template>
    <div class="parent">
        <div class="child1">
            noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib
        </div>
        <div class="child2">
            noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib
        </div>
        <div class="child3">
            noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib noushedul islam akib
        </div>
    </div>
</template>
<style scoped>
.parent{
    display: grid;
    grid-template-areas: 
    'a b c';
    grid-gap: 20px;
}
.child1{
    grid-area: a;
}
.child2{
    grid-area: b;
}
.child3{
    grid-area: c;
}
@media (max-width: 500px){
    .parent{
        grid-template-areas: 
        'a'
        "b"
        'c';
        grid-gap: 20px;
    }
}
</style>