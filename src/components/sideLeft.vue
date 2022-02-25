<template>
    <div class="side package">
        <clSVG></clSVG>
        <div class="side-container">
            <div class="left top"><a href="/">
                    <logoSVG></logoSVG>
                </a></div>
            <div class="middle left">
                <div class="service-info">
                    <template v-if="tab=='student'">
                    <div class="service-info__title"> Ещё не участвуете в партнерской программе? </div>
                    <div class="service-info__icon">
                        <moneySVG></moneySVG>
                    </div>
                    <div class="service-info__text">Создайте пассивный источник дохода. Мы обучаем, вы
                        зарабатываете. Никаких продаж! Активируйте <b>демо-доступ за 0,99$</b> и получите пошаговую
                        инструкцию
                        как зарабатывать вместе с нами на онлайн-образовании.</div>
                    <div class="service-info__btn"><a href="/register/index.html"
                            class="btn btn-rounded btn-shadow btn-shadow-yellow btn-green">Активировать сейчас</a>
                    </div>
                    </template>
                    <template v-else>
                        <div class="service-info__title"> Готовы стать нашим студентом и изменить
                            свою к жизнь к лучшему? </div>
                        <div class="service-info__icon">
                            <peopleSVG></peopleSVG>
                        </div>
                        <div class="service-info__text">Мы на 100% уверены в пользе нашего
                            обучения. Поэтому предоставляем доступ к демо-неделе <b>совершенно бесплатно</b>, чтобы
                            вы лично смогли убедиться в качестве программы, понять насколько готовы работать над
                            собой и воплощать свои желания.</div>
                        <div class="service-info__btn"><a
                                href="/register/index.html"
                                class="btn btn-rounded btn-shadow btn-shadow-yellow btn-green">Начать бесплатно</a>
                        </div>
                    </template>
                </div>
                <a href="/" class="back-to-side-btn"> Вернуться на главную </a>
            </div>
        </div>
    </div>
</template>

<script>
import clSVG from './svg/circle-left'
import logoSVG from './svg/logo'
import moneySVG from './svg/money'
import peopleSVG from './svg/people'
export default {
    props: {
        tab: {
            type: String,
            default: 'student'
        }
    },
    components: {clSVG, logoSVG, moneySVG, peopleSVG}
}
</script>

<style lang="scss">
.service-info {
    margin-top: 2.77rem;
    text-align: center;

    &__title {
        color: #fae870;
        font-size: 2rem
    }

    &__icon {
        margin: 40px auto;
        max-width: 200px;
        max-height: 185px;

        @media (max-width:767px) {
            max-width: 100px
        }
    }
    &__text {
        margin-bottom: 3.33rem
    }
}

</style>