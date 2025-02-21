<template>
    <header class="banner">
        <div>
            <img src="../assets/images/Logo.png" alt="Logo do Projeto" class="logo" />

            <p class="header-lg header-phrase">
                <span class="text-header">
                    Um banquete de ideias para
                </span>
                despertar o chef que há em você!
            </p>

            <p class="subtitle-lg">
                Explore novas receitas todos os dias com ingredientes que estão ao seu alcance!
            </p>

        </div>
        <div class="">
            <img src="../assets/images/Banner-image.png" alt="" class="banner-image" />
        </div>
    </header>
</template>

<style scoped>
.banner {
  padding: 4rem 7.5rem;
  color: var(--cream);
  display: flex;
  justify-content: space-between;
  align-items: center;
  column-gap: 3.25rem;
}

.logo {
  height: 4.5rem;
  margin-bottom: 3rem;
}

.header-phrase {
  margin-bottom: 2rem;
}

.text-header {
  color: var(--medium-green);
}

.banner-image {
  width: 35rem;
}

@media only screen and (max-width: 1300px) {
  .banner {
    padding: 4rem 3.75rem;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  .logo {
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
}


@media only screen and (max-width: 767px) {
  .banner {
    padding: 4rem 1.5rem;
  }

  .banner-image {
    width: min(100%, 21.25rem);
  }
}
</style>