<script>
let bsDisabled  = {
    install(Vue)
    {
        Vue.directive('bs-disabled', bsDisabled);
    },
    bind(el, binding, vnode)
    {
        bsDisabled.action(el, binding, vnode);
    },
    update(el, binding, vnode)
    {
        bsDisabled.action(el, binding, vnode);
    },
    inserted(el, binding, vnode)
    {
        if(binding.value === true || binding.value.condition === true)
        {
            if(binding.modifiers.hidden || (binding.value && binding.value.hidden === true))
                if(binding.value.busy !== true)
                    bsDisabled.hideNode(vnode);
        }
    },
    hideNode(vnode)
    {
        vnode.elm.parentElement.removeChild(vnode.elm);
    },
    action(el, binding, vnode)
    {
        if(binding.value === true || binding.value.condition === true)
        {
            el.disabled = true;
            el.classList.add('disabled');
        }
        else
        {
            el.disabled = false;
            el.classList.remove('disabled');
        }
    }
}
export default bsDisabled;
</script>
