<template>
    <div class="about-container">
        <p>Passionné par le développement web et le design, je suis un créatif curieux et impliqué. Spécialisé dans le digital, mon approche allie une réflexion centrée sur l’utilisateur à la création d’univers graphiques inédits</p>
        <a href="#" class="primary-btn">Se connecter sur Linkedin<span class="arrow-right"><ConnectIcon/></span></a>
        <a href="#" class="primary-btn">Télécharger mon CV<span class="arrow-right"><DownloadCvIcon/></span></a>
    </div>
</template>

<script setup>
import ConnectIcon from '@/assets/icons/connectlinkedin.svg'
import DownloadCvIcon from '@/assets/icons/downloadcv.svg'
</script>

<style lang="scss">
@use '../styles/main.scss';
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
}
</style>