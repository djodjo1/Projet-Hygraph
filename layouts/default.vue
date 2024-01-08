<template>
  <Head>
    <Title>Parfum Femur</Title>
    <Meta name="description" content="Parfum Femur |  Explorez l'élégance olfactive à travers nos parfums exquis et plongez dans un univers où chaque note révèle une histoire sensorielle unique.  </TextesSubHeader>

" />
<Meta
      property="og:description"
      content="Parfum Femur | Explorez l'élégance olfactive à travers nos parfums exquis et plongez dans un univers où chaque note révèle une histoire sensorielle unique.                  </TextesSubHeader>
."
    />
    <Meta
      property="og:image"
      content="./public/img/header.jpg"
    />
    <Meta
      property="og:url"
      
    />
    <Meta property="og:type" content="website" />
    <Meta property="og:locale" content="fr_FR" />
    <Meta property="og:site_name" content="Parfum Femur" />
    <Meta name="twitter:card" content="summary_large_image" />
    <Meta name="twitter:site" content="@CastorObese" />
    <Meta name="twitter:creator" content="@CastorObese" />
    <Meta name="twitter:title" content="Parfum Femur" />
    <Meta
      name="twitter:description"
      content="Parfum Femur | Explorez l'élégance olfactive à travers nos parfums exquis et plongez dans un univers où chaque note révèle une histoire sensorielle unique.                  </TextesSubHeader>
."
    />
    <Meta name="theme-color" content="#1f2937" />
  </Head>
  <LayoutsBase>
    <template #navigation>
      <NavsNav>
        <template #logo>
          <TitresLogo><img src="../public/img/logo-parfumfemur.svg" width="50" height="auto"> </TitresLogo>
        </template>

        <template #links>
          <LinksNavLink to="/">Accueil</LinksNavLink>
              <LinksNavLink to="/entreprise">Entreprise</LinksNavLink>
              <LinksNavLink to="/services">Services</LinksNavLink>
          <LinksNavLink to="/equipe">Équipe</LinksNavLink>
          <LinksNavLink to="/blogactualite">Blog</LinksNavLink>
          <LinksNavLink to="/contact">Contact</LinksNavLink>

        </template>
      </NavsNav>
    </template>

    <template #content>
      <slot />
    </template>

    <template #footer>
      <FootersBasic />
    </template>
  </LayoutsBase>
</template>
