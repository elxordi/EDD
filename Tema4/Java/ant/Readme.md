#   **Ant**

Crearemos la calculadora
```
package com.ieseljust.edd.calc;

public class Calculadora {

    private float lastResult;
    private String lastOp;

    public float getLastResult(){
        return this.lastResult;
    }

    public String getLastOp(){
        return this.lastOp;
    }

    public float suma(float op1, float op2){
        float result=op1+op2;
        this.lastResult=result;
        this.lastOp="Suma";

        return result;
    }

    public float resta(float op1, float op2){
        float result=op1-op2;
        this.lastResult=result;
        this.lastOp="Resta";

        return result;
    }

    public float multiplica(float op1, float op2){
        // Fem els càlculs
        float result=op1*op2;

        // Actualitzem els atributs de la classe
        this.lastResult=result;
        this.lastOp="Multiplica";

        // I finalment retornem els resultats
        return result;
    }

    public float divideix(float op1, float op2){
        // Fem els càlculs
        float result=op1/op2;

        // Actualitzem els atributs de la classe
        this.lastResult=result;
        this.lastOp="Divideix";

        // I finalment retornem els resultats
        return result;
    }

Calcula 

El fixero es el Calcula.java:
```
package com.ieseljust.edd.calc;

import com.ieseljust.edd.calc.Calculadora;

public class Calcula {
    private static float operand1;
    private static float operand2;

    public static void main(String[] args) {
        if (args.length != 2) {
            System.out.println("\nSintaxi incorrecta. Necessite dos números.");
            System.exit(-1);
        }

        operand1=Float.parseFloat(args[0]);
        operand2=Float.parseFloat(args[1]);

        Calculadora myCalc=new Calculadora();

        System.out.println("La suma entre "+operand1+" i "+operand2+" és "+myCalc.suma(operand1, operand2));
        System.out.println("La resta entre "+operand1+" i "+operand2+" és "+myCalc.resta(operand1, operand2));
        System.out.println("La multiplicació entre "+operand1+" i "+operand2+" és "+myCalc.multiplica(operand1, operand2));
        System.out.println("La divisió entre "+operand1+" i "+operand2+" és "+myCalc.divideix(operand1, operand2));
        System.out.println("Última operació realitzada: "+myCalc.getLastOp()+"; Últim resultat: "+myCalc.getLastResult());
    }
}
 ```
Copilació i execució

1.Pondremos de forma individual:

$ javac com/ieseljust/edd/calc/Calculadora.  java

$ javac com/ieseljust/edd/calc/Calcula.java

2.Copilar directament tots els fitxers .java del directori calc:

$ javac com/ieseljust/edd/calc/*.java
```
# **2. Apache Ant**

Fixer build.hml

<project>
    <target name="clean">
        <delete dir="classes" />
    </target>

    <target name="compile" depends="clean">
        <mkdir dir="classes" />
    <javac includeantruntime="false" srcdir="com/ieseljust/edd/calc" destdir="classes" />
    </target>

    <target name="run" depends="compile">
        <java classpath="classes" classname="com.ieseljust.edd.calc.Calcula">
            <arg value="${arg0}"/>
            <arg value="${arg1}"/>
        </java>

    </target>
</project>




# **2.3. Ús d´Ant**

Farem:
```
$ ant compile
Buildfile: /home/joamuran/Dropbox/Docencia/curs_19-20/EDD/Unitats/UD4. Automatitzacio/exemples_java/calcula/build.xml

clean:

compile:
    [mkdir] Created dir: /EDD/Tema4/Java/ant 

    [javac] Compiling 2 source files to /home/joamuran/Dropbox/Docencia/curs_19-20/EDD/Tema4/Java/ant 

BUILD SUCCESSFUL
Total time: 1 seconds
```