<template>
    <transition name="modal-animation">
      <div v-show="modalDefaultActive" class="fixed w-full h-full top-0 left-0 flex items-center justify-center">
        <div class="modal-overlay absolute z-50 w-full h-full bg-gray-900 opacity-50"></div>
            <div class="bg-white w-11/12 md:max-w-md mx-auto rounded shadow-lg z-50 overflow-y-auto">
                <div class="modal-content py-4 text-left px-6">
                <slot />
            </div>
        </div>
    </div>
</transition>
</template>
  
<script>
    export default {
        props: ["modalDefaultActive"],
        setup(props, { emit }) {
        const close = () => {
            emit("close");
        };
        return { close };
        },
    };
</script>