<script lang="ts">
import { defineComponent, h } from 'vue';

export default defineComponent({
    render() {
        const defaultSlot = this.$slots.default ? this.$slots.default() : [];
        const content = defaultSlot.map((vnode) => {
            if (vnode.type === 'ul') {
                return h('details', { class: 'sub-menu' }, vnode);
            } else {
                return vnode;
            }
        });
        return (
            h('nav', {
                class: 'menu'
            }, content)
        );
    }
})
</script>
