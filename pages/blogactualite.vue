<script setup>
const query = gql`
    query Blogs {
        blogs(orderBy: id_ASC) {
            id
            slug
            titre
            description
            prix
            image {
                id
                url(
                    transformation: {document: {output: {format: webp}}}
                )
            }
        }
    }
`;

const blogs = ref();
const { data } = await useAsyncQuery(query);
blogs.value = data.value.blogs.map(blog => ({ ...blog, expanded: false }));
</script>

<template>
    <Container>
        <TitresH2><i class="ri-list-indefinite"></i> Nos services parfumés</TitresH2>
        <div v-if="blogs" class="grid grid-cols-2 gap-6">
            <div v-for="blog in blogs" :key="blog.id">
                <div class="mb-9 block rounded-lg bg-white shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700">
                    <div class="relative overflow-hidden bg-cover bg-no-repeat">
                        <img class="rounded-t-lg w-full object-cover h-32 sm:h-40 lg:h-48" :src="blog.image.url" alt="" />
                    </div>
                    <div class="flex flex-col justify-between p-6 items-center">
                        <div>
                            <h5 class="mb-2 text-xl font-sans font-medium leading-tight text-neutral-800 dark:text-neutral-50">
                                {{ blog.titre }}
                            </h5>
                            <p class="font-serif mb-4 pr-2 text-base text-neutral-600 dark:text-neutral-200">
                                {{ blog.expanded ? blog.description : blog.description.slice(0, 100) + '...' }}
                            </p>
                        </div>
                        <button @click="toggleExpansion(blog)" class="bg-primary hover:bg-primary-dark text-white px-4 py-2 rounded-full focus:outline-none focus:shadow-outline-primary border border-black">
                            {{ blog.expanded ? 'Réduire' : 'Voir plus' }}
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </Container>
</template>

<script>
function toggleExpansion(blog) {
    blog.expanded = !blog.expanded;
}
</script>
