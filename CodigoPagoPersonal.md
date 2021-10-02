# Codigo-trabajo-parcial-
import java.util.Scanner;

public class PagoPersonal {

	static double CalcularPagoPolo(int [] horas){
        		
		double suma=0;
		double poloTarifa[] = new double[10];
		
		//Rendimiento de las 10 operaciones del polo
		poloTarifa[0]=4.16; // union_hombro
		poloTarifa[1]=1.25; // cerrado_cuello
		poloTarifa[2]=5.81; // pegado_cuello
		poloTarifa[3]=5;    // tapete_hombro
		poloTarifa[4]=4.16; // basta_manga
		poloTarifa[5]=7.12; // pegar_manga
		poloTarifa[6]=8.33; // cerrado_costado
		poloTarifa[7]=5;    // atraque_puño
		poloTarifa[8]=5;    // basta_faldon
		poloTarifa[9]=8.33; // inspeccion
		
		for (int i = 0; i < poloTarifa.length; i++) {
			suma += horas[i]*poloTarifa[i];
		}     
		
        return suma;
    }
	
	
	static double CalcularPagoPantalon(int [] horas){
		
		double suma=0;
		double pantalonTarifa[] = new double[10];
		
        //Rendimiento de las 10 operaciones del pantalon
		pantalonTarifa[0] = 6.66; //cerrar_tiro
		pantalonTarifa[1] = 12.5; //cerrado_costado
		pantalonTarifa[2] = 11.1; //cerrar_entrepierna
		pantalonTarifa[3] = 4.16; //cerrar_puño
		pantalonTarifa[4] = 11.11;//pegar_puño
		pantalonTarifa[5] = 4.16; //cerrar_pretina
		pantalonTarifa[6] = 10;   //pegar_pretina
		pantalonTarifa[7] = 8.33; //recubierto_pretina
		pantalonTarifa[8] = 5.0;  //pegar_etiqueta
		pantalonTarifa[9] = 8.33;
		
		for (int i = 0; i < pantalonTarifa.length; i++) {
			suma += horas[i]*pantalonTarifa[i];
		} 
        
        return suma;
        
    }
	
	static double CalcularPagoPolera(int [] horas){
		
		double suma=0;
		double poleraTarifa[] = new double[9];
		
        //Rendimiento de las 10 operaciones del poleras
		poleraTarifa[0] = 4.16; //union_de_hombro
		poleraTarifa[1] = 8.33; //pegar_manga
		poleraTarifa[2] = 10.00;//cerrar_costado
		poleraTarifa[3] = 4.16; //cerrar_puño
		poleraTarifa[4] = 11.11;//pegar_puño
		poleraTarifa[5] = 1.38; //cerrar_cuello
		poleraTarifa[6] = 5.81; //pegar_cuello
		poleraTarifa[7] = 5.43; //recubierto_cuello
		poleraTarifa[8] = 8.33; //inspeccion
		
		for (int i = 0; i < poleraTarifa.length; i++) {
			suma += horas[i]*poleraTarifa[i];
		}
        
        return suma;
    }
	
	static double CalcularPagoBoxer(int [] horas){
		
		double suma=0;
		double boxerTarifa[] = new double[8];
		
        //Rendimiento de las 10 operaciones del boxer
		boxerTarifa[0] = 5.43; //cerrar_tiro
		boxerTarifa[1] = 5.00; //recubierto_tiro
		boxerTarifa[2] = 8.33; //cerrar_costado
		boxerTarifa[3] = 6.66; //recubierto_costado
		boxerTarifa[4] = 11.11;//basta_bota
		boxerTarifa[5] = 8.33; //pegar_elastico
		boxerTarifa[6] = 6.66; //recubierto_elastico
		boxerTarifa[7] = 6.66; //inspeccion
        
		for (int i = 0; i < boxerTarifa.length; i++) {
			suma += horas[i]*boxerTarifa[i];
		}
        
        return suma;
    }
	
	
	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		
		int polo[] = new int[10];
		int pantalon[] = new int[10];
		int polera[] = new int[9];
		int boxer[] = new int[8];
		
		// Solicitamos el nombre y codigo de la persona
		System.out.println("Insertar nombre de trabajador: ");
		String nombre= sc.nextLine();
		System.out.println("Insertar codigo de trabajador: ");
		String codigo= sc.nextLine();
		
		// Solicitamos el llenado de horas para cada operacion por cada tipo de prenda
		System.out.println("Ingrese la cantidad de horas por cada operacion de Polos respectivamente:\n" +
                "1. union de hombro\n" +
                "2. cerrado de cuello\n" +
                "3. pegado de cuello\n" +
                "4. tapete de hombro\n" +
                "5. basta de manga\n" +
                "6. pegar manga\n" +
                "7. cerrado de costado\n" +
                "8. atraque de puño\n" +
                "9. basta faldon\n" +
                "10. inspeccion");
		for (int i = 0; i < polo.length; i++) {
	        polo[i] = sc.nextInt();
		}
		
		
		System.out.println("Ingrese la cantidad de horas por cada operacion de Pantalones respectivamente:\n" +
                "1. cerrar tiro\n" +
                "2. cerrado costado\n" +
                "3. cerrar entrepierna\n" +
                "4. cerrar puño\n" +
                "5. pegar puño\n" +
                "6. cerrar pretina\n" +
                "7. pegar pretina\n" +
                "8. recubierto pretina\n" +
                "9. pegar etiqueta\n" +
                "10. inspeccion");
		for (int i = 0; i < pantalon.length; i++) {
	        pantalon[i] = sc.nextInt();
		}
		
		System.out.println("Ingrese la cantidad de horas por cada operacion de Poleras respectivamente:\n" +
                "1. union de hombro\n" +
                "2. pegar manga\n" +
                "3. cerrar costado\n" +
                "4. cerrar puño\n" +
                "5. pegar puño\n" +
                "6. cerrar cuello\n" +
                "7. pegar cuello\n" +
                "8. recubierto cuello\n" +
                "9. inspeccion");
		for (int i = 0; i < polera.length; i++) {
	        polera[i] = sc.nextInt();
		}
 
		System.out.println("Ingrese la cantidad de horas por cada operacion de Boxers respectivamente:\n" +
                "1. cerrar tiro\n" +
                "2. recubierto tiro\n" +
                "3. cerrar costado\n" +
                "4. recubierto costado\n" +
                "5. basta bota\n" +
                "6. pegar elastico\n" +
                "7. recubierto elastico\n" +
                "8. inspeccion");
		for (int i = 0; i < boxer.length; i++) {
	        boxer[i] = sc.nextInt();
		}
		
		//Ejecutamos el calculo de los pagos por cada tipo de prenda
		
		double resultPolo = CalcularPagoPolo(polo);
		double resultPantalon = CalcularPagoPantalon(pantalon);
		double resultPolera = CalcularPagoPolera(polera);
		double resultBoxer = CalcularPagoBoxer(boxer);
		
		System.out.println("Para el trabajador "+nombre+" con codigo "+codigo);
		System.out.println("Pago subtotal polos : "+ resultPolo);
		System.out.println("Pago subtotal pantalones : "+ resultPantalon);	
		System.out.println("Pago subtotal poleras : "+ resultPolera);
		System.out.println("Pago subtotal boxers : "+ resultBoxer);
		System.out.println("Pago total a recibir : "+(resultPolo+resultPantalon+resultPolera+resultBoxer));

	}

}
