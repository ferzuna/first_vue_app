<script setup>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger"

gsap.registerPlugin(ScrollTrigger);

document.addEventListener('DOMContentLoaded', () => {
    const sections = gsap.utils.toArray('section');
    let scrollTween = gsap.to(sections, {
        xPercent: -100 * (sections.length - 1),
        ease: 'none',
        scrollTrigger: {
            trigger: '.wrapper',
            pin: true,
            scrub: 0.5,
            snap: 1 / (sections.length - 1),
            start: 'top top',
            end: 3000,
        }
    })

    gsap.to('.logo', {
        fontSize: '2.5rem',
        top: '4rem',
        scrollTrigger: {
            trigger: '.logo',
            start: 'top top',
            end: 1500,
            scrub: 0.5,
        }
    })

    gsap.to('.line', {
        height: '10rem',
        scrollTrigger: {
            trigger: '.line',
            scrub: 0.5,
            start: 'center center',
            end: 2000
        }
    })

    document.querySelectorAll('.character').forEach(el => {
        gsap.to(el.querySelector('.caption'), {
            x: 0,
            y: 0,
            scrollTrigger: {
                containerAnimation: scrollTween,
                trigger: el.querySelector('.caption'),
                start: 'top bottom',
                end: '+=1000',
                scrub: 0.5,
            }
        })

        gsap.to(el.querySelector('.quote'), {
            y:0,
            ease: 'none',
            scrollTrigger: {
                containerAnimation: scrollTween,
                trigger: el.querySelector('.quote'),
                start: 'top bottom',
                end: '+=20%',
                scrub: 0.5,
            }
        })

        gsap.to(el.querySelector('.nickname'), {
            y:0,
            ease: 'none',
            scrollTrigger: {
                containerAnimation: scrollTween,
                trigger: el.querySelector('.nickname'),
                start: 'top bottom',
                end: '+=10%',
                scrub: 0.5,
            }
        })

        gsap.to(el.querySelector('.block'), {
            x:0,
            ease: 'none',
            scrollTrigger: {
                containerAnimation: scrollTween,
                trigger: el.querySelector('.block'),
                start: 'top bottom',
                end: '+=' + window.innerWidth,
                scrub: 0.5,
            }
        })
        gsap.to(el.querySelector('img'), {
            y:0,
            ease: 'none',
            scrollTrigger: {
                containerAnimation: scrollTween,
                trigger: el.querySelector('img'),
                start: 'top bottom',
                end: '+=50%',
                scrub: 0.5,
            }
        })

        gsap.to(el.querySelector('.huge-text'), {
            y:0,
            ease: 'none',
            scrollTrigger: {
                containerAnimation: scrollTween,
                trigger: el.querySelector('.huge-text'),
                start: 'top bottom',
                end: '+=100%',
                scrub: 0.5,
            }
        })
    })
    
})
</script>

<template>
    <div class="logo">
        <h1>one<br/>punch<br/>man</h1>
    </div>

    <div class="wrapper">
        <section class="intro">
            <div class="line"></div>
        </section>
        <section class="saitama character">
            <div class="block"></div>
            <img src="/src/assets/saitama.png" alt=""><span class="huge-text">Saitama</span>
            <div class="caption">
                Saitama is a fictional character and the main protagonist of the Japanese manga and anime series, "One-Punch Man." He is a bald, ordinary-looking man who trained himself to become an extremely powerful superhero. Despite his lack of outward appearance, he possesses immense strength, speed, and durability that allow him to defeat any opponent with a single punch.
            </div>
            <div class="nickname"><span>Nickname</span>Bald Cape</div>
            <div class="quote">
                I'll leave tomorroow's problems to tomorrow's me
            </div>
        </section>

        <section class="genos character">
            <div class="block"></div>
            <img src="/src/assets/genos.png" alt=""><span class="huge-text">Genos</span>
            <div class="caption">
                Genos is a fictional character from the Japanese manga and anime series, "One-Punch Man." He is a cyborg and the disciple of Saitama, the series' main protagonist. Genos was once a human, but after his hometown was destroyed by a mysterious villain, he was badly injured and almost died. In order to survive, he agreed to become a cyborg and was transformed into a powerful weapon.
            </div>
            <div class="nickname"><span>Nickname</span>Demon Cyborg</div>
            <div class="quote">
                I will not grow if i cannot face superior opponents
            </div>
        </section>
    </div>
</template>