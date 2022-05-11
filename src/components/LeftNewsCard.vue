<template>
    <div class="title-block">
        {{title}}
        <ul class="data">
        <li>Сегодня</li>
        <li>2351</li>
        <li>36  </li>
    </ul>
    </div>
    
</template>


<script>
export default {
    props: {
        title: String
    },
    data() {
        return {

        }
    }

}
</script>

<style >
.title-block {
    padding: 12px 0;
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 131.25%;
    color: #2b2b2b;
    border: black;
}

.data {
    margin: 10px 0 10px 0;
    margin-top: 5px;
    display: flex;
    flex-direction: row;
    color: #575757;
    font-size: 12px;
}
</style>