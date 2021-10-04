<template>
    <div>
        <ul>
            <li v-for="li in mypropsName" :key="li">
                {{li}}
            </li>
        </ul>
    </div>
</template>
<script>
export default{
     props: {
        mypropsName: {
            type: Array,
            required: true
        }
    }
}
</script>
