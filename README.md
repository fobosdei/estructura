package trabajo;

import java.util.HashMap;

public class Modificar {

    static String cadenaejemplo = "los pecados capitales";
    static HashMap<Long, Long> memo = new HashMap<>();

    public static void main(String[] args) {
        System.out.println("La cadena de ejemplo tiene como longitud:");
        System.out.println(contarCaracteres(cadenaejemplo) + " caracteres");
        System.out.println("Cadena invertida:");
        System.out.println(invertirCadena(cadenaejemplo));
       //iteracion
        long N = 4; 
        System.out.println("Fibonacci de " + N + " es: " + fibbo_rec(N));
        
    }

    public static int contarCaracteres(String cadena) {
        if (cadena.isEmpty()) {
            return 0;
        } else {
            return 1 + contarCaracteres(cadena.substring(1));
        }
    }

    public static String invertirCadena(String cadena) {
        if (cadena.isEmpty()) {
            return "";
        } else {
            return invertirCadena(cadena.substring(1)) + cadena.charAt(0);
        }
    }

    public static int contarCaracterEnCadena(char car, String cadena) {
        if (cadena.isEmpty()) {
            return 0;
        } else {
            int count = cadena.charAt(0) == car ? 1 : 0;
            return count + contarCaracterEnCadena(car, cadena.substring(1));
        }
    }

    public static long fibbo_rec(long N) {
        if (N <= 1) {
            return N;
            
        }
        if (memo.containsKey(N)) {
                return memo.get(N);	
            } else {
                long fibonacci = fibbo_rec(N - 1) + fibbo_rec(N - 2);
                memo.put(N, fibonacci); 
                return fibonacci;
            }
        
      
        }
    }
    

