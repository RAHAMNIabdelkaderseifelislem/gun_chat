<script>
    import { user } from "./user";

    let username;
    let password;

    function login() {
        user.auth(username,password, ({ err })=> err && alert(err));
    }

    function signup() {
        user.create(username,password, ({ err })=>{
            if(err){
                alert (err);
            }else{
                login();
            }

        });
    }
</script>

<label for="username">Username</label>
<input name="username" bind:value={username} minlength="10" maxlength="32">
<label for="password">Password</label>
<input type="password" name="password" bind:value={password}>

<button class="login" on:click={login()}>Login</button>
<button class="signup" on:click={signup()}>Signup</button>