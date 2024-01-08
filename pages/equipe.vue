<script setup>
const query = gql`
    query Membres {
        membres(orderBy: id_ASC) {
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

const membres = ref();
const { data } = await useAsyncQuery(query);
membres.value = data.value.membres;
</script>

<template>
    <Container>
        <TitresH2><i class="ri-list-indefinite"></i> Nos services parfumés</TitresH2>
        <div v-if="membres" class="grid grid-cols-1 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-2 xl:grid-cols-3 gap-6">
            <div v-for="membre in membres" :key="membre.id">
                <div class="mb-9 block rounded-lg bg-white shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700">
                    <div class="relative overflow-hidden bg-cover bg-no-repeat">
                        <img class="rounded-t-lg w-full object-cover h-32 sm:h-40 lg:h-48" :src="membre.image.url" alt="" />
                    </div>
                    <div class="flex flex-col justify-between p-6 items-center">
                        <div>
                            <h5 class="mb-2 text-xl font-sans font-medium leading-tight text-neutral-800 dark:text-neutral-50">
                                {{ membre.titre }}
                            </h5>
                            <p class="font-serif mb-4 pr-2 text-base text-neutral-600 dark:text-neutral-200">
                                {{ membre.description }}
                            </p>
                        </div>
                       
                    </div>
                </div>
            </div>
        </div>
    </Container>
</template>
