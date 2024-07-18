<template>
  <section id='about'>
        <h1 className='about__h1'>About Me</h1>
        <p>현재 서울 관악구 신림동에 거주중입니다.</p>
        <div className='about__container'>

          <!-- {/* for desktop */} -->
          <ul className='about__menu-text'>
            <li className='li_active'>2014 ~ 2015 : 학원 수료</li>
            <li>2015 ~ 2016 : 회사 뉴테크 근무</li>
            <li>2016 ~ 2019 : 타 직업 종사</li>
            <li>2019 ~ 2020 : ERP 프로젝트</li>
            <li>2020 ~ 2020.10 : 구직 & 개인프로젝트</li>
            <li>2020.10 ~ 2020.05 : 인텔렉투스 근무</li>
          </ul>

          <!-- {/* for mobile */} -->
          <select className='about__menu-select'>
            <option value='0'>2014 ~ 2015 : 학원 수료</option>
            <option value='1'>2015 ~ 2016 : 회사 뉴테크 근무</option>
            <option value='2'>2016 ~ 2019 : 타 직업 종사</option>
            <option value='3'>2019 ~ 2020 : ERP 프로젝트</option>
            <option value='4'>2020 ~ 2020.10 : 구직 & 개인프로젝트</option>
            <option value='5'>2020.10 ~ 2020.05 : 인텔렉투스 근무</option>
          </select>

          <div id='content' className='about__detail'>
            <p>약 6개월, 비트컴퓨터 학원 수료했습니다.</p>

            <p className='ct_deactive'>
            모니터링시스템 중 네이버 기사 크롤링 구현
              <br /> 신한 O2O 프로젝트 중 각 화면구현과 이미지 업로드 구현
              <br /> 그리드 순서변경 구현
            </p>
            <p className='ct_deactive'>
              간간히 책을 읽으면서
              <br />
              레노버 콜센터에서 3개월
              <br /> 인조대리석 1년
              <br /> 구매자재팀에서 창고관리 1년
              <br /> 그렇게 일해보니 개발일이 저에게 제일 잘 맞았다고
              생각됐습니다.
            </p>

            <p className='ct_deactive'>
              위쉬정보기술에 취직하였습니다.
              <br />
              태영건설에 파견되었습니다.
              <br />
              2019년 4월부터 2020년 4월까지 1년 1개월동안
              <br />
              차세대 ERP 프로젝트에서 구매자재 업무 중 구매를 담당했습니다.
            </p>

            <p className='ct_deactive'>
              구직활동을 하기도 했지만 리액트로 sub project를 해야겠다는 생각이 들었습니다.
              <br />
              그래서 포트폴리오 사이트와 블로그를 개발했습니다.
            </p>

            <p className='ct_deactive'>
              Vue.js를 사용하여
              <br />
              다양한 프로젝트에서 프론트엔드를 담당했습니다.
              <br />
              2021년 4월 28일, 가톨릭 수도자로의 진로변경 고민을 이유로
              <br />
              퇴사통보를 하고 5월 31일까지 근무하였습니다.
              <br />
              그리고 7월 20일까지 고민끝에 수도자는 제 길이 아니라고 판단하고
              <br />
              다시 개발일을 시작하려고 합니다.
              
            </p>

            <!-- {/* <p className='ct_deactive'>
              구직활동을 하기도 했지만 리액트로 sub project를 해야겠다는 생각이 들었습니다.
              <br />
              그래서 포트폴리오 사이트와 블로그를 개발했습니다.
            </p> */} -->
          </div>
        </div>
      </section>
</template>

<script>
export default {
    mounted () {
        const listElements = document.querySelectorAll(".about__menu-text li") // as NodeListOf<Element>
        const selectElement = document.querySelector(".about__menu-select") //as HTMLSelectElement;

        // li click 이벤트 바인딩
        listElements.forEach((li, index) => {
            li.addEventListener("click", () => {
                this.setActive(li, listElements);
                this.bindingContent(listElements, li);
                //select box 의 선택된 값을 변경한다.
                selectElement.value = index + "";
            });
        });

        // select box click 이벤트 바인딩
        selectElement.addEventListener("change", (e) => {
            const target = e.target //as HTMLSelectElement;
            const index = target.selectedIndex;
            // 선택된 select box 의 값에 해당하는 li 요소를 변수에 할당한다.
            const li = listElements[index];
            this.setActive(li, listElements);
            this.bindingContent(listElements, li);
        });
    },
    data: function() {
        return {
            msg: "Hello World"
        }
    },
    methods: {
        setActive(target, listElements) {
            listElements.forEach((element) => {
                element.classList.remove("li_active");
            });
            target.classList.add("li_active");
        },
        bindingContent(lis, clickedElement) {
            const text = clickedElement.textContent;
            lis.forEach((ele, index) => {
                const p = document.querySelectorAll(".about__detail p");

                if (ele.textContent === text) {
                    p[index].classList.remove("ct_deactive");
                } else {
                    p[index].classList.add("ct_deactive");
                }
            });
        }
    }
}
</script>

<style lang="scss" scoped>
%flex-column-center {
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* ABOUT */
#about {
  @extend %flex-column-center;
  background-color: #ebebeb;
  width: 100%;
}

.about__h1 {
  font-size: 30px;
  font-weight: 700;
  padding-top: var(--bet-padding);
}

.about__h2 {
  text-align: center;
}

.about__container {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  padding-top: var(--bet-padding);
  padding-bottom: var(--bet-padding);

  & .about__menu-text {
    float: right;
    padding-right: 50px;
    font-size: 20px;

    & li {
      padding: 10px 0;
    }

    & li:hover {
      color: #e31b6d;
      cursor: pointer;
    }
  }

  & .about__menu-select {
    display: none;
  }

  & .about__detail {
    width: 50vw;
    background-color: #ffffff;
    height: 225px;
    border-radius: 0.5em;
    display: flex;
    flex-direction: column;
    justify-content: center;
    & p {
      margin: 20px;
      text-align: center;
      line-height: 1.7;
    }
  }
}

//common??
.li_active {
  color: #e31b6d;
  cursor: pointer;
}

.ct_deactive {
  display: none;
}

@media screen and (max-width: 620px) {
  .about__container {
    flex-direction: column;
    // justify-content: space-between;

    & .about__menu-text {
      display: none;
    }

    & .about__detail {
      width: 80vw;
      height: 250px;
    }

    & .about__menu-select {
      display: inline-block;
      width: 80vw;
      padding: 0.8em 0.5em;
      border: 1px solid #999;
      font-family: inherit;
      background: url(https://farm1.staticflickr.com/379/19928272501_4ef877c265_t.jpg)
        no-repeat 95% 50%; /* 네이티브 화살표 대체 */
      border-radius: 0px;
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none;
      margin-bottom: 10px;
    }
  }
}

</style>