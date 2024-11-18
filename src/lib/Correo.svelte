<script>
    let email ='';
    let isValid = false;

    function validateEmail(){
        const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
        isValid = regex.test(email);
    }
</script>
<div class = "container">
    <p>Input Validación</p>
    <input type="email" bind:value={email} on:input={validateEmail}/>
    <p>{isValid ? 'Email válido' : 'Email no válido'}</p>
</div>