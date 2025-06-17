<template>
    <div class="about-container" id="about">
        <div>
            <p>Passionné par le développement web et le design, je suis un créatif curieux et impliqué. Spécialisé dans
                le digital, mon approche allie une réflexion centrée sur l’utilisateur à la création d’univers
                graphiques inédits</p>
            <div class="button-group">
                <a href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/" target="_blank"
                    class="primary-btn" aria-label="M'ajouter sur Linkedin">Se connecter sur Linkedin<span class="arrow-right">
                        <ConnectIcon />
                    </span></a>
                <a href="#" target="_blank" class="primary-btn" aria-label="Télécharger mon CV">Télécharger mon CV<span class="arrow-right">
                        <DownloadCvIcon />
                    </span></a>
            </div>
        </div>
    </div>
</template>

<script setup>
import ConnectIcon from '@/assets/icons/connectlinkedin.svg'
import DownloadCvIcon from '@/assets/icons/downloadcv.svg'
</script>

<style lang="scss">
@use '@/styles/global.scss' as *;

.about-container {
    background-color: $color-primary;

    div {
        padding: 6rem 2rem;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;

        p {
            color: $color-secondary;
            font-size: 1.5rem;
            margin-bottom: 2rem;
        }

        .button-group {
            padding: 0;
            display: flex;
            flex-direction: column;

            a {
                svg {
                    width: 20px;
                    height: 20px;
                }
            }
        }
    }
}

@media (min-width: 1280px) {
    .about-container div {
        max-width: 920px;
        margin: 0 auto;
        padding: 10rem 0rem;

        p {
            font-size: 2.5rem;
            font-weight: 700;
        }

        .button-group {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: row;
            align-items: flex-start;
            justify-content: flex-start;
            gap: 2rem;
        }
    }
}
</style>