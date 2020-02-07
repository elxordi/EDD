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

}
Anem a explicar-lo per parts:

En primer lloc, s'indica el nom del paquet al què pertany el programa, de forma completa. Fixeu-se que ve definit per l'estructura de directoris on es troba:
package com.ieseljust.edd.calc;
Després es defineix la classe Calculadora. Recordeu que en Java tot ha d'estar dins una classe, tant el main com les funcions (mètodes) que definim. L'estructura general d'aquesta classe Calculadora és la següent (mostrem només algunes parts):
public class Calculadora {

    private float lastResult;
    private String lastOp;

    public float getLastResult(){ ... }

    ...

    public float suma(float op1, float op2){ ... }
    }
}