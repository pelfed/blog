<template>
    <header class="my-16">
        <router-link v-if="! noHome" tag="button" to="/" class="group flex items-center text-gray-600 mb-2 focus:outline-none">
            <Icon icon="arrow-thin-left-circle" class="w-6 h-6 mr-1" primary="text-white" secondary="group-hover:text-gray-900"></Icon>
            <div class="uppercase tracking-wider font-semibold text-sm group-hover:text-gray-900">Home</div>
        </router-link>

        <div class="text-gray-800 font-serif text-4xl md:text-5xl font-semibold leading-tight" v-text="effectiveTitle"></div>
        <div class="text-gray-800 font-serif text-xl md:text-2xl font-medium" v-if="effectiveSubtitle" v-text="effectiveSubtitle"></div>
    </header>
</template>

<script>
export default {
    props: {
        title: String,
        subtitle: String,
        noHome: Boolean,
    },
    computed: {
        effectiveTitle () {
            return this.title || this.$page.title
        },
        effectiveSubtitle () {
            return this.subtitle || this.$page.frontmatter.subtitle
        },
    }
}
</script>
