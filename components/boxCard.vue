<template>
    <div className="movies-card">
        <div className="card-content">
            <h1>{{newBox.title}}</h1>
            <div>{{newBox.selected}}</div>
            <div>{{newBox.weight}}</div>
            <div>{{newBox.technology}}</div>
            <div>{{newBox.msg}}</div>
        </div>
    </div>

</template>

<script>
import Form from './boxForm.vue';
export default {
    name: "boxCard",
    props:['newBox'],
    components: { Form }
}

</script>