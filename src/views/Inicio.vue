<template lang="pug">
section
  .banner-principal.mb-5
    .container.tarjeta.p-4.p-sm-5(
      :style="{'background-image': `url(${require('@/assets/curso/fondo-banner-principal.png')})`}"
    )
      .row.justify-content-around.align-items-center
        .col-lg-7.col-xxl-6.banner-principal__info
          .banner-principal__programa
            .h1.mb-0 Desarrollo de habilidades digitales para experiencias seguras en línea
          
          .h2 Información del programa
          .banner-principal__datos
            ul
              li.mb-3.banner-principal__datos__item
                p.h6.mb-0.me-3.banner-principal__datos__item__titulo Nombre del programa: 
                p.banner-principal__datos__item__texto Desarrollo de habilidades digitales para experiencias seguras en línea
              li.mb-3.banner-principal__datos__item
                p.h6.mb-0.me-3.banner-principal__datos__item__titulo Código: 
                p.banner-principal__datos__item__texto 23310013
              li.mb-3.banner-principal__datos__item
                p.h6.mb-0.me-3.banner-principal__datos__item__titulo Total Horas: 
                p.banner-principal__datos__item__texto 48 horas
              li.mb-3.banner-principal__datos__item
                p.h6.mb-0.me-3.banner-principal__datos__item__titulo Duración en semanas: 
                p.banner-principal__datos__item__texto N/A
              li.mb-3.banner-principal__datos__item
                p.h6.mb-0.me-3.banner-principal__datos__item__titulo Modalidad: 
                p.banner-principal__datos__item__texto virtual

        .d-none.d-lg-block.col-lg-5
          //- img(src="@/assets/curso/banner-princiapal.svg")
          .video
            | <iframe data-v-1f9e4816="" width="560" height="315" src="https://www.youtube.com/embed/2L91WMqw96A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="allowfullscreen"></iframe>


  .container.tarjeta.tarjeta__template--azul-claro.p-4.p-md-5.mb-5(data-aos="fade-up")
    .titulo__template--a.mb-4
      span.h4 2. Justificación<br>del programa
    p.mb-3  Los entornos económicos y sociales han tenido que adaptarse a la dinámica generada por los avances tecnológicos y la transformación digital aunado a la situación actual del mundo y particularmente en Colombia, como lo menciona el documento del observatorio laboral El COVID19 y el mercado de trabajo en Colombia, así la imposibilidad para regresar a los ambientes tradicionales ha exigido, laboral y profesionalmente, la necesidad de contar con entornos remotos para solventar los retos de la contingencia, trayendo consigo un aumento en la demanda de un conjunto de ocupaciones en ámbitos tales como la transformación digital, la telemedicina, el <i>marketing</i> digital y demás espacios que tienen el potencial de quedarse en nuestras vidas de manera permanente.
    p.mb-3  Asimismo, en la recuperación de la economía actividades como el diseño gráfico ha hecho aportes relevantes, a futuro plantea la importancia de la inteligencia artificial, educación en la nube o el comercio electrónico como claves del desarrollo, en tal sentido, el SENA diseñó la <b>“Ruta de  fortalecimiento de las habilidades digitales para la vida y la productividad”</b>, de las cuales este curso trabaja la <b>Seguridad de la información</b> como cuarto programa de la ruta de aprendizaje, la cual brinda elementos conceptuales y herramientas que permitan desarrollar y fortalecer habilidades en la era digital para que los ciudadanos puedan adaptarse a las necesidades de las empresas y de la sociedad, que son parte de las competencias propuestas por la industria 4.0, además de ser un aporte que propicie el desarrollo y fortalecimiento de posibles emprendimientos sostenibles.
  .container.tarjeta.tarjeta__template--azul-claro.p-4.p-md-5.mb-5(data-aos="fade-up")
    .titulo__template--a.mb-4
      span.h4 3. Población<br>objetivo

    p El curso está dirigido a profesionales, tecnólogos y técnicos en salud que requieren conocer elementos conceptuales y normativos para implementar procesos y procedimientos operativos básicos que garanticen una atención en salud integral, oportuna y de calidad a las víctimas de ataque con agentes químicos.

  .container.tarjeta.tarjeta__template--azul-claro.p-4.p-md-5.mb-5(data-aos="fade-up")
    .titulo__template--a.mb-4
      span.h4 3. Estrategia<br>metodológica

    p Centrada en la construcción de la autonomía para garantizar la calidad de la formación en el marco de la formación por competencias, el aprendizaje por proyectos y el uso de técnicas didácticas activas que estimulan el pensamiento para la resolución de problemas simulados y reales; soportadas en la utilización de las tecnologías de la información y la comunicación, integradas en ambientes virtuales de aprendizaje, que en todo caso recrean el contexto productivo y vinculan al aprendiz con la realidad cotidiana y el desarrollo de las competencias.
      br
      br
      | Las estrategias didácticas integradoras están basadas en situaciones reales que le permitirán poner en marcha los contenidos conceptuales y procedimentales, aplicando sus conocimientos y habilidades para resolver un problema, frente a la atención integral de urgencias a víctimas de ataque con agentes químicos.
      br
      br
      | Igualmente, debe estimular de manera permanente la autocrítica y la reflexión del aprendiz sobre el quehacer y los resultados de aprendizaje que logra a través de la vinculación activa de las cuatro fuentes de información para la construcción de conocimiento:

  //- Créditos
  .container.tarjeta.tarjeta__template--azul-claro.p-4.p-md-5.mb-5(data-aos="fade-up")
    .titulo__template--a.mb-4
      span.h4 Créditos

    
    .creditos
      div(
        v-for="(creditoKey, index) of Object.keys(creditosData)"
        :class="index != Object.keys(creditosData).length -1 ? 'mb-4' : ''" 
      )
        .creditos__titulo {{configTitulos[creditoKey]}}
        table
          tbody
            tr(
              v-for="(item, idx) of creditosData[creditoKey]" 
              :key="creditoKey+idx"
            )
              td.text-bold(colspan='2' v-html="renderText(item.nombre)")
              td(colspan='2' v-html="renderText(item.cargo)")
              td(colspan='3' v-html="renderText(item.centro)")

  Footer

</template>
<script>
export default {
  name: 'Inicio',
  data: () => ({
    configTitulos: {
      liderEquipo: 'ECOSISTEMA DE RECURSOS EDUCATIVOS DIGITALES',
      contenidoInstruccional: 'CONTENIDO INSTRUCCIONAL',
      desarrolloProducto:
        'DISEÑO Y DESARROLLO DE RECURSOS EDUCATIVOS DIGITALES',
      gestoresRepositorio: 'GESTORES DE REPOSITORIO',
    },
  }),
  computed: {
    creditosData() {
      return this.$config.creditos
    },
  },
  methods: {
    renderText(textObj) {
      let newText = ''
      if (Array.isArray(textObj)) {
        textObj.forEach((texto, index) => {
          newText += (index ? '<br/>' : '') + texto
        })
      } else {
        newText += textObj
      }
      return newText
    },
  },
}
</script>

<style lang="sass">
.creditos
  td, th
    border-color: $color-sistema-c
</style>
