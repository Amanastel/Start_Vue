<template>
    <div class="post-form">
        <h2>Create A new post</h2>
        <form @submit.prevent="onSubmit">
        <div class="form-group">
            <label for="username">Username</label>
            <input
            type="text"
            id="username"
            class="form-control"
            v-model="username"
            placeholder="Enter username"
            required
            />
        </div>
        <div class="form-group">
            <label for="caption">Caption:</label>
            <textarea
            id="caption"
            class="form-control"
            v-model="caption"
            placeholder="Enter caption"
            required
            ></textarea>
        </div>
        <button type="submit" class="btn btn-primary">Submit</button>
        </form>
    </div>
</template>

<script>
export default {
    name: "PostForm",
    data() {
        return {
            username: "",
            caption: ""
        };
    },
    methods: {
        onSubmit() {
            if (this.username && this.caption){
                const newPost = {
                    username: this.username,
                    caption: this.caption,
                    likes: 0,
                    comments: []
                };
                this.$emit("new-post", newPost);
                this.username = "";
                this.caption = "";
            }
            else{
                alert("Please fill in username and caption");
            }
        }
    }
};
</script>

<style scoped>

#post_form{
    margin-top: 20px;
    margin-bottom: 20px;
}

input[type=text], textarea {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    margin-top: 6px;
    margin-bottom: 16px;
}

input[type=submit] {
    background-color: #4CAF50;
    color: white;
    padding: 12px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

input[type=submit]:hover {
    background-color: #45a049;
}

</style>