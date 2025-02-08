<script>
    let name = '';
    let email = '';
    let username = '';
    let password = '';

    function signUp() {
        const user = { name, email, username, password };

        let users = JSON.parse(localStorage.getItem('users')) || [];

        users.push(user);

        localStorage.setItem('users', JSON.stringify(users));

        window.location.href = '/login';
    }
</script>

<div class="container h-full mx-auto flex justify-center items-center">
    <div class="space-y-10 text-center flex flex-col items-center relative">
        <h2 class="h2">Sign Up Page</h2>
        <!-- Animated Background -->
        <figure>
            <section class="img-bg" />
        </figure>
        <!-- / -->
        <div class="flex flex-col space-y-4 w-80">
            <input type="text" placeholder="Name" class="input-field p-2 border rounded-md text-black" bind:value={name} />
            <input type="text" placeholder="Email" class="input-field p-2 border rounded-md text-black" bind:value={email} />
            <input type="text" placeholder="Username" class="input-field p-2 border rounded-md text-black" bind:value={username} />
            <input type="password" placeholder="Password" class="input-field p-2 border rounded-md text-black" bind:value={password} />
            <button class="btn variant-filled w-full p-2 rounded-md" on:click={signUp}>Sign Up</button>
        </div>
    </div>
</div>

<style lang="postcss">
</style>
