<template>
  <section id='home'>
        <div className='home__container'>
          <div className='home__title'>
            Full stack web developer.
            <br />
            최종호
          </div>
          <div id='goTo__about' className="home__button nav__btn">
            <!-- className={"home__button nav__btn"} -->
            View my work <i className='fas fa-arrow-right'></i>
          </div>
        </div>
      </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
%flex-column-center {
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Home */
#home {
  @extend %flex-column-center;
  background-color: #0c2a40;
  height: calc(100vh + 53px);
  width: 100%;
  top: 0;
  position: relative;
  justify-content: center;
}

.home__container {
  @extend %flex-column-center;
}

.home__title {
  color: white;
  font-size: 24pt;
  margin-bottom: 20px;
}

.home__button {
  border: 2px solid #fff;
  cursor: pointer;
  font-size: 13pt;
  padding: 10px 20px;
  color: white;
  margin-bottom: 53px;

  -webkit-transition: background-color 0.5s ease;

  &:hover {
    background-color: #04c2c9;
    -webkit-transition: background-color 0.5s ease;
  }

  & > i {
    -webkit-transition: transform 0.5s ease;
  }

  &:hover > i {
    transform: rotate(90deg);
    -webkit-transition: transform 0.5s ease;
  }

  & i {
    padding: 5px;
  }
}

@media screen and (max-width: 380px) {
  .home__container {
    width: 90%;
  }
  .home__title {
    text-align: center;
  }
}
</style>