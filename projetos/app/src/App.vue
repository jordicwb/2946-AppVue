<template>
  <div>
      <!-- Nav bar  -->
      <nav class="navbar navbar-dark bg-primary justify-content-between flex-nowrap flex-row">
        <div class="container">
          <router-link to="/" class="navbar-brand float-left">12956-Vue</router-link>
          <ul class="nav navbar-nav flex-row float-right">
            <li class="nav-item">
              <router-link to="/" class="nav-link px-3">Novo Produto</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/view" class="nav-link">Listar Produtos</router-link>
            </li>
          </ul>
        </div>
      </nav>
      
    <!-- Router view -->
    <div class="container mt-5">
      <router-view>
        
      </router-view>
    </div>
  </div>

</template>