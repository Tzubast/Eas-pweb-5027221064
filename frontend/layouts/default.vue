<template>
    <nav>
      <div class="navbar">
        <div class="nav-links" :class="{ opened: menuIsActive }">
            <i class="bx bx-x" @click="menuEventButton"></i>
          <ul class="links">
            <li><NuxtLink to="/"><a href="#">Home<hr /></a></NuxtLink></li>
            <li><NuxtLink to="/submissionbyemail"><a href="#">Check Status<hr /></a></NuxtLink></li>
          </ul>
        </div>
      </div>
    </nav>
  
    <div>
      <slot />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        menuIsActive: false,
      };
    },
    methods: {
      menuEventButton() {
        this.menuIsActive = !this.menuIsActive;
      },
    },
  };
  </script>
  
  <style scoped>
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 70px;
      background: linear-gradient(135deg, #242524, #0b5ed7);
      z-index: 100000;
    }
  
    nav .navbar {
      height: 100%;
      max-width: 1200px;
      margin: auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 50px;
    }
  
    nav .navbar .nav-links .links li a {
    font-family: 'Arial', sans-serif;
    font-size: 18px;
    font-weight: 500;
  }
  
    nav .navbar .nav-links .links {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0; /* Remove default margin */
      padding: 0; /* Remove default padding */
    }
  
    nav .navbar .nav-links .links li {
      position: relative;
      display: flex;
      align-items: center;
      list-style: none;
      padding: 0 14px;
    }
  
    nav .navbar .nav-links .links li a {
      height: 100%;
      color: #fff;
      text-decoration: none;
      white-space: nowrap;
      font-size: 16px;
      font-weight: 500;
      border-bottom: 0px solid transparent;
      transition: all 0.4s ease;
    }
  
    nav .navbar .nav-links .links li:hover a {
      color: #04ed93;
    }
  
    nav .navbar .nav-links .links li a hr {
      width: 0px;
      display: hidden;
      border: none;
      border-radius: 70px;
      height: 1.8px;
      background: #04ed93;
      transform: translateY(-1300%);
      transition: all 0.4s ease;
    }
  
    nav .navbar .nav-links .links li:hover a hr {
      display: block;
      width: 100%;
      transition: all 0.4s ease;
    }
  
    nav .navbar .bx-menu,
    nav .navbar .nav-links .sidebar-logo .logo_name,
    nav .navbar .sidebar-logo img,
    nav .navbar .nav-links .sidebar-logo .bx-x {
      display: none;
    }
  
    .button-login {
      background: #0d6efd;
      border: 1px solid #0d6efd;
      color: #fff;
      width: 80px;
      padding: 6px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
      transition: all 0.2s ease;
    }
  
    .button-login:hover {
      border: 1px solid #0b5ed7;
      background: #0b5ed7;
    }
  
    .sidebar-button-login {
      display: none;
    }
  
    @media (max-width: 954px) {
      nav .navbar {
        max-width: 100%;
        padding: 0 25px;
      }
      nav .navbar .nav-links .links li {
        padding: 0 10px;
      }
      nav .navbar .nav-links .links li a {
        font-size: 15px;
      }
    }
  
    @media (max-width: 800px) {
      nav .navbar .nav-links {
        display: block;
        position: fixed;
        background: #242524;
        top: 0;
        left: 0;
        max-width: 100%; /* Updated to 100% */
        width: 100%;
        padding: 20px;
        line-height: 40px;
        transition: all 0.4s ease;
      }
  
      .logoImg {
        display: none;
      }
  
      nav .navbar .nav-links.opened {
        /* Updated to 0 */
        left: 0;
      }
  
      nav .navbar .nav-links .sidebar-logo {
        display: flex;
        justify-content: space-between;
        align-items: center;
      }
      nav .navbar .bx-menu,
      nav .navbar .nav-links .sidebar-logo .logo_name,
      nav .navbar .nav-links .sidebar-logo .bx-x {
        color: #04ed93;
        font-size: 25px;
        font-weight: 500;
        display: block;
      }
  
      nav .navbar .sidebar-logo img {
        width: 50px;
        height: 50px;
        display: block;
      }
  
      nav .navbar .nav-links .links {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 20px;
      }
  
      .button-login {
        display: none;
      }
      .sidebar-button-login {
        display: inline-block;
        background: #0d6efd;
        border: 1px solid #0d6efd;
        color: #fff;
        width: 80px;
        padding: 6px;
        border-radius: 5px;
        cursor: pointer;
        font-size: 16px;
        margin-top: 15px;
      }
    }
  </style>
  