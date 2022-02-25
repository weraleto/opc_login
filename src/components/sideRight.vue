<template>
    <div class="side form">
        <crSVG></crSVG>
        <div class="side-container">
            <div class="right top">
                <div>Просто стать лучше.</div>
            </div>
            <div class="middle right">
                <div class="register-form">
                    <div class="register-form-types">
                        <a v-for="b in btns" :key="b.tab" 
                        @click="tab=b.tab" href="#" 
                        class="register-form-types__item"
                        :class="{'active': tab == b.tab}"
                        >
                        {{b.name}}
                        </a>
                    </div>
                    <div class="register-form-title">
                        <h1>Войти как {{header[tab]}}</h1>
                        <p class="register-form-authorize"><a href="/register/index.html">Зарегистрироваться</a></p>
                    </div>
                    <form action="" class="register-form-content">
                        <div class="register-form-content__item">
                            <div class="register-form-content__label">Email</div>
                            <div class="register-form-content__input"><input type="email"
                                    placeholder="Введите ваш email"></div>
                        </div>
                        <div class="register-form-content__item">
                            <div class="register-form-content__label">Пароль</div>
                            <div class="register-form-content__input"><input type="password"
                                    placeholder="Введите ваш пароль"></div>
                        </div>
                        <div class="register-form-content__item subline"><label role="radio" tabindex="0"
                                class="el-radio"><span class="el-radio__input"><span
                                        class="el-radio__inner"></span><input type="radio" aria-hidden="true"
                                        tabindex="-1" class="el-radio__original" value="1"></span><span
                                    class="el-radio__label">Запомнить меня
                                    <!----></span></label><a href="#" class="forgot-pass">Забыли пароль?</a></div>
                        <div class="register-form-content__submit"><button
                                class="btn btn-primary btn-rounded btn-shadow btn-shadow-yellow">Войти</button></div>
                    </form>
                </div><a href="/" class="back-to-side-btn"> Вернуться на главную </a>
            </div>
        </div>
    </div>
</template>

<script>
import crSVG from './svg/circle-right'

export default {
    components: {crSVG},
    data: ()=>{
        return {
            tab: 'student',
            header: {
                student: 'студент',
                partner: 'партнер',
            }, 
            form: {
                email: null,
                password: null,
            },
            btns: [
                {name: 'Вход для студентов', tab: 'student'},
                {name: 'Вход для партнеров', tab: 'partner'},
            ]
        }
    },
    watch: {
        tab(val){
            this.$emit('change_tab', val)
        }
    }
}
</script>

<style lang="scss">


.register-form {
    margin-top: 2.77rem;
    width: 100%;

    &-types {
        display: flex;
        justify-content: space-between;
        margin-bottom: 2.44rem;

        &__item {
            background-color: #c4c4c4;
            padding: 11px 5px;
            text-align: center;
            width: 100%;
            font-size: 14px;
            max-width: calc(50% - 4.5px);
            box-shadow: 0 4px 4px rgba(0, 0, 0, .1);

            &.active {
                background-color: #0073fa;
                color: #fff
            }
            &:first-child {
                border-radius: 40px 0 0 40px
            }
            &:last-child {
                border-radius: 0 40px 40px 0
            }
        }
    }

    &-title {
        text-align: center;
        margin-bottom: 2.77rem;
        h1 {
            font-size: 2rem
        }
    }

    &-authorize {
        font-size: 14px;
        color: #c4c4c4;
        text-decoration: underline;
        margin-top: 1rem;
        color: #0073fa
    }

    &-content {
        &__item {
            max-width: calc(100% - 70px);
            margin: 0 auto 29px;
            &.subline {
                display: flex;
                align-items: center;
                justify-content: space-between;
                text-align: left;
                margin-top: 28px;
                margin-bottom: 50px
            }

            @media (max-width:575px) {
                max-width: 100%;
            }
        }
        &__label {
            margin-bottom: 6px;
            color: #0073fa;
            padding-left: 18px
        }
        &__submit {
            text-align: center
        }
    }

    
}

.forgot-pass {
    font-size: 14px;
    color: #c4c4c4;
    text-decoration: underline;

    &:hover {
        color: #4a4a49
    }

    @media (max-width:380px) {
        font-size: 12px;
    }
}



</style>