<script>
    let username = '';
    let password = '';

    function login() {
        let users = JSON.parse(localStorage.getItem('users')) || [];

        const user = users.find(u => u.username === username && u.password === password);

        if (user) {
            window.location.href = '/home';
        } else {
            alert('Invalid username or password');
        }
    }
</script>

<div class="container h-full mx-auto flex justify-center items-center">
    <div class="space-y-10 text-center flex flex-col items-center relative">
        <a href="/" class="absolute btn variant-filled" style="top: 0; left: 0; margin: 10px 0 0 10px; padding: 10px 20px;">Back</a>
        <h2 class="h2">Login Page</h2>
        <!-- <button class="btn variant-filled w-full p-2 rounded-md" on:click={login}>Login</button> -->
        <!-- Animated Background -->
        <figure>
            <section class="img-bg" />
        </figure>
        <!-- / -->
        <div class="flex flex-col space-y-4 w-80">
            <input type="text" placeholder="Username" class="input-field p-2 border rounded-md text-black" bind:value={username} />
            <input type="password" placeholder="Password" class="input-field p-2 border rounded-md text-black" bind:value={password} />
            <button class="btn variant-filled w-full p-2 rounded-md" on:click={login}>Login</button>
        </div>
    </div>
</div>

<style lang="postcss">
</style>
