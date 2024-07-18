<template>
  <nav id='navbar' className='notFixed'>
        <div className='navbar__menu'>
          <ul>
            <li id='nav__home' className='nav__btn active'>
              Home
            </li>
            <li id='nav__about' className='nav__btn'>
              About
            </li>
            <li id='nav__skills' className='nav__btn'>
              Skills
            </li>
            <li id='nav__work' className='nav__btn'>
              My Work
            </li>
            <li id='nav__contact' className='nav__btn'>
              Contact
            </li>
          </ul>
        </div>
      </nav>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
/* Navbar */
#navbar {
  width: 100%;
  height: 50px;
  bottom: 0px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #0a2336;
  border-bottom: 3px solid #04c2c9;
  z-index: 1;
}

.notFixed {
  position: absolute;
}

.fixed {
  bottom: inherit;
  left: 0;
  position: fixed;
  top: 0;
}

.navbar__menu {
  padding-left: 50px;
  position: sticky;

  & ul {
    color: white;
    display: flex;
  }

  & li {
    margin-right: 50px;
    font-size: 20px;
  }

  & li:hover {
    color: #e31b6d;
    cursor: pointer;
  }

  & li.active {
    color: #e31b6d !important;
    cursor: pointer;
  }
}

@media screen and (max-width: 620px) {
  #navbar {
    justify-content: center;
    box-sizing: border-box;
  }
  .navbar__menu {
    width: 80vw;
    padding-left: 0;

    justify-content: center;
    & ul {
      display: table;
      margin: 0 auto;

      & li {
        float: left;
        margin: 0 5vw;
      }

      & li:hover {
        color: white;
      }
    }
  }
}

</style>