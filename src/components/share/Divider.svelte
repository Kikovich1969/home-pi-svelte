<script>
    export let deviderText = "Devider";
</script>

<div class="divider">
    <div class="devider-line"><hr /></div>
    <div class="devider-text">{deviderText}</div>
    <div class="devider-line"><hr /></div>
</div>

<style>
    .divider {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 2rem 0;
    }

    .devider-line {
        width: 100%;
    }

    .devider-text {
        font-size: .8rem;
        text-transform: uppercase;
        padding: .3rem .6rem;
        letter-spacing: .1rem;
    }

    hr {
        border: 0;
        border-bottom: 1px solid #ccc;
        background: #999;
    }
</style>