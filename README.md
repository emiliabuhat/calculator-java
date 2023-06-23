  Pentru calcularea numarului de linii din cod a celor 3 fisiere am folosit metoda Calculate Metrics din  IntelliJ IDEA. 
  Pentru fisierul “LICENSE” nu a fost recunoscut un cod astfel ca nu avem un numar de linii de cod pentru acest fisier, iar pentru celelalte fisiere LOC reprezinta 150.
	Pentru calcularea complexitatii ciclomatice si cognitive am utilizat aceeasi metoda Calculate Metrics, iar rezultatul pentru complexitatea cognitiva a fost 37 iar pentru cea ciclomatica 24. Aceste rezultate au fost afisate doar pentru fisierul „Calculator”.
	In urma revizuirii informale si a analizei statice a codurilor din fisierele date am identificat urmatoarele aspecte:
Calculator-53- „for” loop can be replaced with enhanced for loop,  dupa optimizarea codului bucla for arata asa: 
for (String number : numbers) {

    if (number.equals("-Infinity")) {
        numberList.add(Float.NEGATIVE_INFINITY);
    } else if (number.equals("Infinity")) {
        numberList.add(Float.POSITIVE_INFINITY);
    } else {

        try {
            numberList.add(Float.parseFloat(number));
        } catch (Exception exc) {
            return "ERROR";
        }
    }
}

Calculator- 70- local variable „textResult” is redundant, se poate inlocui aceasta linie cu return Float.toString(finalResult); 
Calculator-87- Common part can be extracted from if, avertizarea apare pentru a optimiza codul, astfel optimizarea acestei secvente este: if (indexMultiply >= indexDivide) {
    result += numbers.get(indexDivide) / numbers.get(indexDivide + 1);
Calculator- 136- Common part can be extracted from if, pentru optimizare se elimina liniile 144 si 145
Calculator-179-return is unnecessary as the last statement in a void method, functiile void nu returneaza informatii astfel ca nu este necesar sa punem return.

