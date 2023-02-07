<template>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css"
    integrity="sha512-KfkfwYDsLkIlwQp6LFnl8zNdLGxu9YAA1QvwINks4PhcElQSvqcyVLLD9aMhXd13uQjoXtEKNosOWaZqXgel0g=="
    crossorigin="anonymous"
    referrerpolicy="no-referrer"
  />
  <ul>
    <li
      v-for="{ icon, color, id, name } in list"
      :style="`--i: ${id}; --clr: ${color}`"
    >
      <a href="#">
        <span>
          <i :class="`fa-brands ${icon}`"></i>
        </span>
        {{ name }}
      </a>
    </li>
  </ul>
</template>

<script setup lang="ts">
import '/assets/scss/main.scss'

const list = [
  { name: 'Facebook', color: '#1877f2', id: 6, icon: 'fa-facebook-f' },
  { name: 'Whatsapp', color: '#25d366', id: 5, icon: 'fa-whatsapp' },
  { name: 'Twitter', color: '#1da1f2', id: 4, icon: 'fa-twitter' },
  { name: 'Instagram', color: '#c32aa3', id: 3, icon: 'fa-instagram' },
  { name: 'Youtube', color: '#ff0000', id: 2, icon: 'fa-youtube' },
  { name: 'Linkedin', color: '#0a66c2', id: 1, icon: 'fa-linkedin' }
]
</script>

<style scoped lang="scss">
ul {
  position: relative;
  transform: skewY(-15deg);
  li {
    background: #3e3f46;
    list-style: none;
    padding: 15px;
    position: relative;
    transition: 0.5s;
    width: 120px;
    z-index: var(--i);
    span {
      align-items: center;
      display: flex;
      font-size: 1.25em;
      height: 100%;
      justify-content: center;
      left: -40px;
      opacity: 0.5;
      position: absolute;
      top: 0;
      transform-origin: right;
      transform: skewY(45deg);
      transition: 0.5s;
      width: 40px;
    }
    &:last-child::after {
      box-shadow: -120px 120px 20px rgba(0, 0, 0, 0.25);
    }
    a {
      color: #999;
      display: block;
      letter-spacing: 0.05em;
      text-decoration: none;
      text-transform: uppercase;
      transition: 0.5s;
    }
    &:hover {
      transform: translateX(-50px);
      background: var(--clr);
      a {
        color: #fff;
      }
      span {
        opacity: 1;
      }
      &::before {
        background: var(--clr);
        filter: brightness(0.7);
      }
      &::after {
        background: var(--clr);
        filter: brightness(0.9);
      }
    }
    &::before {
      background: #3e3f46;
      content: '';
      height: 100%;
      left: -40px;
      position: absolute;
      top: 0;
      width: 40px;
      filter: brightness(0.7);
      transform-origin: right;
      transform: skewY(45deg);
      transition: 0.5s;
    }
    &::after {
      background: #3e3f46;
      content: '';
      filter: brightness(0.9);
      height: 40px;
      left: 0;
      position: absolute;
      top: -40px;
      transform-origin: bottom;
      transform: skewX(45deg);
      width: 100%;
      transition: 0.5s;
    }
  }
}
</style>
