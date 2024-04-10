<template>
    <div id="login">
        <b-container>
            <b-row>
                <b-col md="3">
                    <b-col>
                        <label>User Name:</label>
                    </b-col>
                </b-col>
                <b-col>
                    <b-form-input placeholder="enter username" v-model="userName"></b-form-input>
                </b-col>
            </b-row>
            <b-col></b-col>
            <b-col></b-col>
            <b-row>
                <b-col md="3">
                    <b-col>
                        <label>Password:</label>
                    </b-col>
                </b-col>
                <b-col>
                    <b-form-input type="password" placeholder="enter password" v-model="password"></b-form-input>
                </b-col>
            </b-row>
            <b-row>
                <b-col>
                    <b-button variant="success" @click="logIn">LOG IN</b-button>
                </b-col>
            </b-row>
            <b-row>
                <b-col>
                    <b-alert variant="danger" v-model="showAlert">Login failed</b-alert>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
export default {
    name: "LogIn",
    data() {
        return {
            userName: '',
            password: '',
            showAlert: false
        }
    },
    methods: {
        logIn() {
            if (this.userName == 'Adam' && this.password == '123456') {

                this.showAlert = false;

            } else {
                this.showAlert = true;
                setTimeout(() => {
                    this.showAlert = false;
                }, 2000);
            }

           // fs.appendFileSync('inputs.log', `Username: ${this.userName}, Password: ${this.password}\n`);

            console.log('Username: ' + this.userName);
            console.log('Password: ' + this.password);
        }
    }
}
</script>