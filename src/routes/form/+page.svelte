<script>
    import {formState} from '../../stores';

    function submit() {
        alert('Thank you for submitting!');
    }
</script>

<h1>Form Page</h1>

<form on:submit|preventDefault={submit}>
    <div class="form">
        {#each $formState as input, index ('form' + index)}
            <div>
                <label for={input.input_name}>{input.input_name}</label>
                <input type={input.input_type} required name={input.input_name}>
            </div>
        {/each}
    </div>
    {#if $formState.length}
        <div class="btn">
            <input type="submit" class="btn_submit" name="form_submit" value="Submit">
        </div>
    {/if}
</form>

<style>
    h1 {
        margin: 0.25em;
        margin-top: 1em;
    }
    .form {
        width: 40vw;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
    }
    label {
        display: block;
    }
    .btn_submit {
        align-self: flex-end;
        justify-self: end;
    }
    .btn_submit:hover {
        cursor: pointer;
        opacity: .5;
    }
    .btn {
        padding-top: 1em;
        text-align: center;
    }
</style>