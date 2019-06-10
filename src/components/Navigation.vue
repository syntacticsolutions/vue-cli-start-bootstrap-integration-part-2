<template>
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top" id="mainNav">
      <div class="container">
        <router-link class="navbar-brand js-scroll-trigger" to="/">Start Bootstrap</router-link>
        <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
          Menu
          <i class="fas fa-bars"></i>
        </button>
        <div class="collapse navbar-collapse" id="navbarResponsive">
          <ul class="navbar-nav text-uppercase ml-auto">
            <li
                class="nav-item"
                v-for="(linkObj, ind) in navList"
                :key="ind"
            >
              <a
                class="nav-link js-scroll-trigger"
                :href="linkObj.path"
                v-if="linkObj.path.indexOf('#') === 0"
            >{{ linkObj.name }}</a>
            <router-link
                class="nav-link js-scroll-trigger"
                v-else
                :to="linkObj.path"
            >{{ linkObj.name }}
            </router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
</template>

<script>
export default {
    data: () => ({
        navList: [
            {
                name: 'Services',
                path: '#services'
            },
            {
                name: 'Portfolio',
                path: '#portfolio'
            },
            {
                name: 'About',
                path: '#about'
            },
            {
                name: 'Team',
                path: '#team'
            },
            {
                name: 'Contact',
                path: '#contact'
            },
            {
                name: 'Blog',
                path: '/blog'
            }
        ]
    })
}
</script>

<style scoped>

#mainNav.navbar {
    background: rgba(0,0,0,0.5);
}


</style>
