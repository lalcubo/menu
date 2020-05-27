<template>
    <sidebar-menu   :menu="menu"
                    :collapsed="collapsed"
                    @toggle-collapse="onToggleCollapse"
                    :style="{'max-width': ancho + 'px'}"
                    />
</template>

<script>
    export default {
        data() {
            return {
                ancho: 380,
                collapsed: true,
                menu: [
                    {
                        header: true,
                        title: 'Menu',
                        hiddenOnCollapse: true,
                    },
                    {
                        //href: '/charts',
                        title: 'Operaciones',
                        icon: 'fa fa-chart-area',
                        child: [
                            {
                                //href: '/charts/sublink',
                                title: 'Procesamiento'
                            },
                            {
                                //href: '/charts/sublink',
                                title: 'Fletes'
                            },
                            {
                                //href: '/charts/sublink',
                                title: 'Recolectas'
                            },
                        ],
                    },
                    {
                        title: 'Administración',
                        icon: 'fas fa-ad',
                        child: [
                            {
                                title: 'Actualización Administrativa',
                                child: [
                                    {
                                    title: 'Inicialización de Envíos Nacionales   '
                                    },
                                    {
                                    title: 'Venta de Contado'
                                    },
                                    {
                                    title: 'Fact. de Guias Prepagada por %',
                                    child: [
                                        {
                                            title: 'Cargar por Guia'
                                        },
                                        {
                                            title: 'Cargar por Archivo'
                                        }
                                        ]
                                    },
                                    {
                                    title: 'Servicio de Protección de Envío'
                                    },
                                    {
                                    title: 'Envio de Aliado'
                                    },
                                ]
                            },
                            {
                                title: 'Caja Chica',
                            },
                            {
                                title: 'Facturación',
                            },
                            {
                                title: 'Pagos y Cobranzas',
                            },
                        ]
                    },
                    {
                        title: 'Gestión de la Calidad',
                        icon: 'fas fa-check',
                        child: [
                            {
                                title: 'Reclamos',
                            }
                        ]
                    },
                    {
                        title: 'Ventas',
                        icon: 'fas fa-comment-dollar',
                        child: [
                            {
                                title: 'Administración de clientes',
                            }
                        ]
                    },
                    {
                        title: 'Sistemas',
                        icon: 'fas fa-laptop',
                        child: [
                            {
                                title: 'Maestros',
                            }
                        ]
                    },
                    {
                        title: 'Reportes',
                        icon: 'far fa-file-pdf',
                        child: [
                            {
                                title: 'Reporte 1',
                            }
                        ]
                    },
                ]
            }   
        },
        mounted(){
            if(this.collapsed)
                this.ancho = 50;
            else
                this.ancho = 380;
        },
        methods: {
            onToggleCollapse(collapsed) {
                if(collapsed){
                    this.ancho = 50;
                }
                else
                    this.ancho = 380;
            },
            onItemClick(event, item) {}
        }
    }
</script>