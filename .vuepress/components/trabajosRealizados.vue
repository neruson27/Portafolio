<template>
    <tbody>
        <div v-for="trabajo in trabajos">
            <h3 class="titulo">{{ trabajo.titulo }}</h3>
            <div class="imagenes">
                <div class="slider">
                    <div class="slide-track">
                        <img v-for="imagen in trabajo.imagenes" class="imagen" v-bind:src="require(`../../static/${imagen}`)" alt="">
                    </div>
                </div>
            </div>
            <p class="descripcion">{{ trabajo.descripcion }}</p>
        </div>
    </tbody>
</template>

<script>
    export default {
        name: 'trabajosRealizados',
        data () {
            return {
                trabajos: [
                    {
                        titulo: 'Merbots',
                        imagenes: ['Merbots.png', 'Merbots2.png', 'Merbots3.png'],
                        descripcion: 'Usando el framework CodeIgniter realize conjunto una persona esta pagina llamada Merbots'
                    },
                    {
                        titulo: 'Orinoco.io',
                        imagenes: ['Orinoco.png', 'Orinoco2.png', 'Orinoco3.png'],
                        descripcion: 'Ayudo constantemente en el desarrollo y actualizacion de esta grandiosa Startup Venezolana con sabor al puedo donde he crecido'
                    },
                    {
                        titulo: 'Wavelets',
                        imagenes: ['Wavele.png', 'Wavele2.jpg', 'Wavele3.png'],
                        descripcion: 'Maquetado Simple para la empresa mexicana Wavelets [Actualmente en remodelacion]'
                    }
                ]
            }
        },
        created () {
        },
        method: {
        }
    }
</script>

<style scoped>
    @keyframes scroll {
        0% { transform: translateX(0); }
        100% { transform: translateX(calc(-280px * 6))}
    }

    .slider {
        background: white;
        box-shadow: 0 10px 20px -5px rgba(0, 0, 0, .125);
        height: 450px;
        margin: auto;
        overflow:hidden;
        position: relative;
        width: 960px;
    }
	
	.slider::before, .slider::after {
		content: "";
		height: 450px;
		position: absolute;
		width: 100px;
		z-index: 2;
	}
	
	.slider::after {
		right: 0;
		top: 0;
		transform: rotateZ(180deg);
	}

	.slider::before {
		left: 0;
		top: 0;
	}
	
	.slide-track {
		animation: scroll 30s linear infinite;
		display: flex;
		width: calc(280px * 3);
	}

    .imagen {
        height: 450px;
		width: 100%;
        margin-right: 3px;
    }
</style>