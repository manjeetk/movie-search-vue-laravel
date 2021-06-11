<template>
<div class="header">
    <header className="header mt-5 rounded">
        <h1>{{ titleText }}</h1>
    </header>
</div>
</template>

<script>
export default {
    name: 'Header',
    props: ['title'],
    setup({title}) {
        return {titleText: title};
    }
}
</script>
