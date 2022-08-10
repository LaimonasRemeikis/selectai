<template>
    <div className="card-admin">
        <header className="header">
            <h1 id="title">Add New Box</h1>
        </header>
        <div id="form-container">
            <div className="question-container">
                <label id="name-label" className="question-label"> Box title </label>
                <input type="text" className="row-input" placeholder="Enter your Box title" required
                    v-model="newBox.title" />
                    <p>{{newBox.title}}</p>
            </div>
            <label id="number-label" className="question-label" value='newBox.selected'> Box Type </label>
            <select v-model="newBox.selected" value="">
                <option  disabled value="">Please select one</option>
                <option>Cotton</option>
                <option>Metal</option>
                <option>Plastic</option>
            </select>
            <div>{{newBox.selected}}</div>
            <div className="question-container">
                <label id="number-label" className="question-label"> Box weight </label>
                <input type="radio" v-model="newBox.weight" value="5kg" />5kg
                <input type="radio" v-model="newBox.weight" value="10kg" />10kg
                <input type="radio" v-model="newBox.weight" value="15kg" />15kg
                <div>{{newBox.weight}}</div>
            </div>
            <div className="question-container">
                <label id="flame" className="question-label">
                    Is Flammable
                </label>
                <input id="isFlammable" value="isFlammable" type="checkbox" className="row-input" v-model="newBox.technology" />
                <label id="number-label" className="question-label">
                    Is Perishable
                </label>
                <input id="isPerishable" type="checkbox" value="IsPerishable" v-model="newBox.technology" />
                <div>{{newBox.technology}}</div>
            </div>
            <div className="question-container">
                <textarea v-model="newBox.msg" className="row-input" name="" id="" cols="30" rows="5"
                    placeholder="Leave your comment here!"></textarea>
                    <div></div>
            </div>
            <div>
                <button @click="addNewBox()" id="submit" type="submit">ADD</button>
                <button type="reset" @click="resetBox()">Reset</button>
            </div>
        </div>
    </div>
</template>
<style lang="sass" scoped></style>

<script>
export default {
    name: "Form",
    data() {
        return {
            newBox: {
                title: "",
                selected: '',
                weight: '',
               technology: [],
                msg: "",
            },
        };
    },
    methods: {
        addNewBox() {
            this.$emit("create-new-box", this.newBox);
            this.resetBox();
        },
        resetBox() {
            this.newBox = {
                title: "",
                selected: '',
                weight: '',
                technology: [],
                msg: "",
            };
        },
    },
};
</script>
