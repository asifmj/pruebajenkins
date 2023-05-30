pipeline
{
    agent any
    environment
    {
    poblacion = 23000
    neto = 0.8
    climaActual = "lluvioso"

    }
    stages
    {
    stage("Mensaje de bienvenida")
    {
    steps
    {
    script
    {
    def fecha = new Date()
    def formatoFecha = new java.text.SimpleDateFormat("yyyy-MM-dd HH:mm:ss")
    def fechaFormateda = formatoFecha.format(fecha)
    def contenido = "Hola , esta es la fecha de hoy:  " + fechaFormateda
    echo contenido
    }

    }
    }
    stage("Calculo de la poblacion y clima")
    {
    steps
    {
    script
    {
    def poblacionNeta = poblacion.toInteger() * neto.toDouble()
    def contenido = "\033[0;1m"+"La poblacion actual es :  " + poblacion + " y tiene un clima : "+ climaActual + "\nY la poblacion neta es :"+poblacionNeta

    echo contenido
    }

    }
    }
    stage("Creacion de fichero")
    {
    steps
    {
    script
    {
    def poblacionNeta = poblacion.toInteger() * neto.toDouble()
    def contenido = "La poblacion actual es :  " + poblacion + " y tiene un clima : "+ climaActual + "\nY la poblacion neta es :"+poblacionNeta
    writeFile(file: "info.txt", text:contenido)
    }

    }
    }
    }

}

