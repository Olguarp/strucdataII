# aplicativo para promediar llamadas diarias
## Ejercicio base:

En mi labor como programador, deseo implementar un software capaz de contar
el numero de llamadas hechas por día durante una semana y promediar 
la cantidad de llamadas que ingresan diariamente para saber cuál es el
número adecuado de asesores para atender llamadas

  Aclaraciones:
- La aplicación solo calcula el número de llamadas diarias recibidas.
- Para efectos de mantener la simplicidad del ejemplo no se contemplan manejar persistencia en el almacenamiento de los datos.
- Los datos deben ser únicamente numéricos para no crear conflicto en la APP.

## Diagrama DFD

![image](https://github.com/Olguarp/strucdataII/assets/129121919/20af1663-92e4-471a-aad8-90311528a873)


## Pseudocódigo
Algoritmo AsesorPOO
    Definir numero_asesores como entero
    Definir losAsesores como arreglo de AsesorPOO
    Definir identificacion, nombre como cadena
    Definir Lunes, Martes, Miercoles como decimal
    Definir promedio como decimal

    Escribir "Digite la cantidad de asesores"
    Leer numero_asesores

    Para i desde 0 hasta numero_asesores hacer
        Escribir "Digite la identificación del asesor"
        Leer identificacion
        Escribir "Digite el nombre del asesor"
        Leer nombre
        Escribir "Digite llamadas Lunes del asesor"
        Leer Lunes
        Escribir "Digite llamadas Martes del asesor"
        Leer Martes
        Escribir "Digite llamadas Miercoles del asesor"
        Leer Miercoles

        crear unAsesor como nuevo AsesorPOO
        unAsesor.identificacion <- identificacion
        unAsesor.nombre <- nombre
        unAsesor.Lunes <- Lunes
        unAsesor.Martes <- Martes
        unAsesor.Miercoles <- Miercoles

        losAsesores[i] <- unAsesor

    Fin Para

    promedio <- 0

    Para i desde 0 hasta numero_asesores hacer
        sum <- (losAsesores[i].Lunes + losAsesores[i].Martes + losAsesores[i].Miercoles) / 3
        promedio <- promedio + sum / numero_asesores
    Fin Para

    Escribir "El promedio es: " + promedio
Fin Algoritmo

## Programación estructurada: EstudianteEstr

import java.util.Scanner;

public class EstudianteEstr
{
    public static void main(String[] args){
        Scanner sc= new Scanner(System.in);
        double[] Lunes = new double [10];
        double[] Martes = new double [10];
        double[] Miercoles = new double [10];
        double[] Jueves = new double [10];
        double[] Viernes = new double [10];
            
        int numero_asesores;
        String nombre_asesor;
        double promedio = 0;
        double LunesC, MartesC, MiercolesC, JuevesC, ViernesC;
        
        System.out.println ("//======//======//======//======//");
        System.out.println("Digite la cantidad de asesores");
        System.out.println ("//======//======//======//======//");
        numero_asesores = sc.nextInt();
        System.out.println ("//======//======//======//======//");
        for (int i = 0; i < numero_asesores; i++){
            System.out.println ("Digite el nombre del asesor");
            nombre_asesor = sc.next();
            System.out.println ("Número de llamadas el Lunes");
            LunesC = sc.nextDouble();
            System.out.println ("Número de llamadas el Martes");
            MartesC = sc.nextDouble();
            System.out.println ("Número de llamadas el Miercoles");
            MiercolesC = sc.nextDouble();
            System.out.println ("Número de llamadas el Jueves");
            JuevesC = sc.nextDouble();
            System.out.println ("Número de llamadas el Viernes");
            ViernesC = sc.nextDouble();
            System.out.println ("//======//======//======//======//");
            Lunes[i]= LunesC;
            Martes[i]= MartesC;
            Miercoles[i]= MiercolesC;
            Jueves[i]= JuevesC;
            Viernes[i]= ViernesC;
        }
        for(int i = 0; i < numero_asesores; i++){
            promedio = promedio + ((Lunes[i] + Martes[i] + Miercoles[i] + Jueves[i] + Viernes[i]) / 5) / numero_asesores;
        }
        System.out.println("El promedio de llamadas es: " + promedio);
    }
}

## POO: Clase principal AsesorPOO

public class AsesorPOO
{
        String identificacion;
        String nombre;
        double Lunes;
        double Martes;
        double Miercoles;
}

Clase Secundaria: Notas
import java.util.Scanner;
public class Notas
{
    public static void main (String[] args){
        
        Scanner sc = new Scanner(System.in);
        int numero_asesores;
        AsesorPOO[] losAsesores = new AsesorPOO[50]; //Se crea un arreglo de objetos
        String identificacion, nombre, curso;
        double Lunes, Martes, Miercoles;
        double promedio = 0;
        System.out.println("Digite la cantidad de asesores");
        numero_asesores = sc.nextInt();
        for (int i = 0; i < numero_asesores; i++){
            System.out.println("Digite la identificación del asesor");
            identificacion = sc.next();
            System.out.println("Digite el nombre del asesor");
            nombre = sc.next();
            System.out.println("Digite llamadas Lunes del asesor");
            Lunes = sc.nextInt();
            System.out.println("Digite llamadas Martes del asesor");
            Martes = sc.nextInt();
            System.out.println("Digite llamadas Miercoles del asesor");
            Miercoles = sc.nextInt();
            AsesorPOO unAsesor /objeto/ = new AsesorPOO();
            unAsesor.identificacion = identificacion;
            unAsesor.nombre = nombre;
            unAsesor.Lunes = Lunes;
            unAsesor.Martes = Martes;
            unAsesor.Miercoles = Miercoles;
            losAsesores[i]= unAsesor;
        }
            
        for(int i = 0; i < numero_asesores; i++){
            double sum = (losAsesores[i].Lunes + losAsesores[i].Martes + losAsesores[i].Miercoles)/3;
            promedio = promedio + sum / numero_asesores;
        }
            
            System.out.println ("El promedio es: " + promedio);
        }
    }

## Diagrama de caso de uso

![image](https://github.com/Olguarp/strucdataII/assets/129121919/43edf309-5472-4d9c-a48f-7db169e5bc48)

## Jira

![image](https://github.com/Olguarp/strucdataII/assets/129121919/ee12f6e2-383f-4bb9-8894-4b60de8695c3)

