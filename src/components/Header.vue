<template>
  <header class="header">
    <div class="container content">
      <a href="#" class="logo-container">
        <img :src="require('@/assets/imgs/logo.svg')" alt="" class="logo">
      </a>

      <div class="menu">
        <ul class="menu-list">
          <li class="item"><a href="#">Sobre Nós</a></li>

          <li class="item has-submenu">
            <a href="#">Serviços</a>

            <ul class="submenu">
              <li class="item"><a href="#">Serviço 1</a></li>
              <li class="item"><a href="#">Serviço 2</a></li>
              <li class="item"><a href="#">Serviço 3</a></li>
              <li class="item"><a href="#">Serviço 4</a></li>
            </ul>
          </li>

          <li class="item"><a href="#">Nosso portfólio</a></li>
          <li class="item"><a href="#">Faça um orçamento</a></li>
        </ul>
      </div>
    </div>
  </header>
</template>


<script>

export default { 
  name: 'PrincipalHeader',
  
}

</script>

<style scoped>

.header {
  padding: 2rem 0;
}

.content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo-container {
  display: block;
  transition: .2s;
}

.logo-container:hover {
  opacity: .8;
  transform: scale(.96);
}

.logo {
  height: 100px;
}

.menu-list {
  display: flex;
  align-items: center;
}

.item { position: relative; }

.item.has-submenu > a {
  padding-right: 1.5rem;
}

.item.has-submenu::after {
  content: '';
  position: absolute;
  right: .5rem;
  top: calc(50% - 1px);
  border: 4px solid transparent;
  border-top-color: var(--secundary);
  transition: .1s;
}

.item > a {
  color: var(--secundary);
  font-weight: 600;
  font-size: 14px;
  transition: .2s;
  padding: .5rem 1rem;
  display: block;
}

.submenu {
  position: absolute;
  left: 10%;
  top: 100%;
  width: 150px;
  background-color: var(--secundary);
  max-height: 0;
  overflow: hidden;
  transition: .15s;
  border-radius: 8px;
  z-index: 99;
}

.menu-list > .item > a:hover { color: var(--principal); }
.menu-list > .item:hover::after { transform: scale(1, -1); top: calc(50% - 6px); border-top-color: var(--principal); }
.item:hover > .submenu { max-height: 200px; }

.submenu .item {
  padding: 0;
}

.submenu .item > a {
  padding: .5rem 1rem;
  display: block;
  color: #FFF;
  font-size: 12px;
}

.submenu .item > a:hover {
  background-color: var(--principal);
}


</style>