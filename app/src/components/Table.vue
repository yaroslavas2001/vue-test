<template>
    <div class="table">
        <div class="_row">
            <div class="cell">№</div>
            <div class="cell">ФИО</div>
            <div class="cell">Профессия</div>
            <div class="cell">Действия</div>
        </div>
        <div class="row">
            <div class="cell__index">{{name}}</div>
            <div class="cell__index">{{name}}</div>
            <div class="cell__index">{{name}}</div>
            <div class="cell__index">{{name}}</div>
        </div>

    </div>
</template>

<script>

export default {
  name: 'Table',
  props: {
    name: String
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.table{
    display: flex;
    flex-direction: column;
}
._row,
.row{
    display: flex;
}

.cell,
.cell__index{
    width: 200px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px #000 solid;
}
</style>
