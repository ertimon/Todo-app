<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Todo app</a>

    <div class="collapse navbar-collapse">
        <ul class="navbar-nav mr-auto">
            <li class="nav-item">
                <nuxt-link exact no-prefetch active-class="active" class="nav-link" to="/">
                    Profile
                </nuxt-link>
            </li>

            <li class="nav-item">
                <nuxt-link active-class="active" class="nav-link" to="/todos">
                    Todos
                </nuxt-link> 
            </li>
        </ul>
    </div>
    </nav>
</template>

