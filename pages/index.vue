<template>
  <div class="bg-gray-200 min-h-screen">
    <hero>
      <!-- Section: Design Block -->
      <section class="relative bg-cover bg-center h-[400px]">
        <!-- Jumbotron -->
        <div class="absolute inset-0 px-4 py-8 text-center md:px-12 lg:text-left">
          <div class="w-full mx-auto sm:max-w-2xl md:max-w-3xl lg:max-w-5xl xl:max-w-7xl">
            <div class="grid items-center gap-8 lg:grid-cols-2 h-full">
              <div class="flex flex-col justify-between h-full bg-white p-8 lg:p-0 lg:bg-transparent lg:w-full lg:h-full lg:rounded-md">
                <div class="mb-6">
                  <TitresH1 class="text-black text-3xl lg:text-4xl"> <br>
                    <span class="italic font-light">Parfum</span> Femur
                  </TitresH1>
                </div>

                <div class="text-black">
                  <TextesSubHeader class="text-sm lg:text-base">
                    Explorez l'élégance olfactive à travers nos parfums exquis et plongez dans un univers où chaque note
                    révèle une histoire sensorielle unique.
                  </TextesSubHeader>

                  <div class="mt-6">
                    <a href="/entreprise">
                      <BoutonsPrimaire>
                        Découvrez notre salon
                        <svg
                          class="rtl:rotate-180 w-3.5 h-3.5 ms-2"
                          aria-hidden="true"
                          xmlns="http://www.w3.org/2000/svg"
                          fill="none"
                          viewBox="0 0 14 10"
                        >
                          <path
                            stroke="currentColor"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M1 5h12m0 0L9 1m4 4L9 9"
                          />
                        </svg>
                      </BoutonsPrimaire>
                    </a>
                  </div>
                </div>
              </div>

              <div class="hidden mb-6 lg:block">
                <!-- Ajoutez ici une image ou utilisez une classe bg-image pour ajouter le fond -->
                <img
                  src="../public/img/header.jpeg"
                  alt="header"
                  class="object-cover w-full h-full rounded-md"
                />
              </div>
            </div>
          </div>
        </div>
      </section>
    </hero>
  </div>
</template>
