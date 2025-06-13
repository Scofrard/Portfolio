<template>
    <div class="about-container">
        <p>Passionné par le développement web et le design, je suis un créatif curieux et impliqué. Spécialisé dans le digital, mon approche allie une réflexion centrée sur l’utilisateur à la création d’univers graphiques inédits</p>
        <a href="#" class="primary-btn">M'ajouter sur Linkedin<span class="arrow-right"><ArrowRightIcon/></span></a>
        <a href="#">Télécharger mon CV<span class="arrow-right"><ArrowRightIcon/></span></a>
    </div>
</template>

<script setup>
import ArrowRightIcon from '@/assets/icons/arrowright.svg'
</script>

<style lang="scss">
.about-container {
    background-color: #9F01FF;
    padding: 6rem 2rem;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;

    p {
        color: #fff;
        font-size: 1.5rem;
        margin-bottom: 2rem;
    }

    a {
    background-color: #FFF;
    padding: .8rem 1.8rem;
    border-radius: 30px;
    text-decoration: none;
    color: black;
    font-weight: 600;
    border: solid 2px #000;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    margin: 1rem 0;
        span {
            svg {
                width: 20px;
                height: 20px;
            }
        }
    }
}
</style>