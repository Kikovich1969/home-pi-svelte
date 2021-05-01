<script>
    export let showModal = false;
    export let isPromo = false;
</script>

{#if showModal}
    <div class="backdrop" on:click|self>
        <div class="modal" class:promo={isPromo}>
            <div class="modal-header">
                <h5 class="modal-title">Modal title</h5>
                <button />
            </div>
            <div class="modal-body">
                <slot />
            </div>
            <div class="modal-footer">
                <button on:click>Close</button>
                <button type="button" class="btn btn-primary">Save changes</button>
            </div>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        position: absolute;
        top: 0;
        left: 0;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.6);
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .modal {
        background-color: white;
        padding: 1rem;
        border-radius: 0.5rem;
        max-width: 60%;
        position: relative;
    }
    .promo {
        background-color: crimson;
        color: white;
    }
</style>
