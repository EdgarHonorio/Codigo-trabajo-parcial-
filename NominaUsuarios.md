# Codigo-trabajo-parcial-
import java.util.Scanner;

public class NominaUsuarios {
	
	//Atributos de la clase
	public String codigos[] = new String[20];
	public String nombres[] = new String[20];
	public String fechas[] = new String[20];
	public int edades[] = new int[20];
	public char sexo[] = new char[20];
	public int numHijos[] = new int[20];
	public String direcciones[] = new String[20];
	
	//Creamos el constructor
	public NominaUsuarios(String[] codigos, String[] nombres, String[] fechas, int[] edades, char[] sexo,int[] numHijos, String[] direcciones) {
		this.codigos = codigos;
		this.nombres = nombres;
		this.fechas = fechas;
		this.edades = edades;
		this.sexo = sexo;
		this.numHijos = numHijos;
		this.direcciones = direcciones;
	}
	
	public String devolverDatos(String codigo) {
		
		String nombre;
		String nacimiento;
		int edad;
		char sex;
		int numHijo;
		String direccion;
		
		for (int i = 0; i < codigos.length; i++) {
			if(codigos[i].equals(codigo)) {
				nombre=nombres[i];
				nacimiento=fechas[i];
				edad=edades[i];
				sex=sexo[i];
				numHijo=numHijos[i];
				direccion=direcciones[i];
				 return "Nombre: "+nombre+", FechaNacimiento: "+nacimiento+", Edad: "+String.valueOf(edad)+", Sexo: "+sex+", NumeroHijos: "+String.valueOf(numHijo)+", Direccion: "+direccion;
			}
		}
		return "No existe usuario con ese codigo";	
	}
	
	public String cantidadVarones() {
		
		int cantidad=0;
		double porcentaje;
		
		for (int i = 0; i < sexo.length; i++) {
			if('H' == sexo[i]) cantidad++;
		}
		porcentaje=cantidad*100/20;
		
		return "La cantidad de varones es "+cantidad+" el cual resepresenta el "+porcentaje+" % del total";	
	}
	
	public String cantidadMujeres() {
		
		int cantidad=0;
		double porcentaje;
		
		for (int i = 0; i < sexo.length; i++) {
			if('M' == sexo[i]) cantidad++;
		}
		porcentaje=cantidad*100/20;
		
		return "La cantidad de mujeres es "+cantidad+" el cual resepresenta el "+porcentaje+" % del total";	
	}
	
	public String numPersonasEdad(int edad) {
		
		if(edad>=0) {
			int edad_igual=0;
			int edad_mayores=0;
			int edad_menores=0;
			
			for (int i = 0; i < edades.length; i++) {
				if(edad == edades[i]) edad_igual++;
				if(edad > edades[i]) edad_menores++;
				if(edad < edades[i]) edad_mayores++;
			}
			
			return "Existen "+edad_menores+" personas con edades menores, "+edad_igual+" con la misma edad y "+edad_mayores+" con edades mayores a "+edad;	
		}else {return "Numero invalido";}
		
	}
	
	public String promedioEdades() {
		
		int sum=0;
		double promedio;
		
		for (int i = 0; i < edades.length; i++) {
			sum += edades[i];
		}
		promedio=sum/20;
		
		return "El promedio de edades es "+promedio;
	}
	
	public String numCantidadHijos(int numero) {
		
		if(numero>=0) {
			int cant_hijos_igual=0;
			int cant_hijos_mayores=0;
			int cant_hijos_menores=0;
			
			for (int i = 0; i < numHijos.length; i++) {
				if(numero == numHijos[i]) cant_hijos_igual++;
				if(numero > numHijos[i]) cant_hijos_menores++;
				if(numero < numHijos[i]) cant_hijos_mayores++;
			}
			
			return "Existen "+cant_hijos_menores+" personas con numero de hijos menores, "+cant_hijos_igual+" con el mismo numero de hijos y "+cant_hijos_mayores+" con numero de hijos mayores a "+numero;
		}else {return "Numero invalido";}
			
	}
	
	public String promedioCantidadHijos() {
		
		int sum=0;
		double promedio;
		
		for (int i = 0; i < numHijos.length; i++) {
			sum += numHijos[i];
		}
		promedio=sum/20;
		
		return "El promedio de cantidad de hijos es "+promedio;
	}
	
	public String mesCumpleaños(String codigo) {
		
		String mes="";
		if(codigo.length()==4) {
			for (int i = 0; i < codigos.length; i++) {
				if(codigos[i].equals(codigo)) {
					mes=fechas[i].substring(3, 5);
					//System.out.println(mes);
				}
			}
		}
		
		switch (mes) {
		case "01":
			mes="Enero";
			break;
		case "02":
			mes="Febrero";
			break;
		case "03":
			mes="Marzo";
			break;
		case "04":
			mes="Abril";
			break;
		case "05":
			mes="Mayo";
			break;
		case "06":
			mes="Junio";
			break;
		case "07":
			mes="Julio";
			break;
		case "08":
			mes="Agosto";
			break;
		case "09":
			mes="Setiembre";
			break;
		case "10":
			mes="Octubre";
			break;
		case "11":
			mes="Noviembre";
			break;
		case "12":
			mes="Diciembre";
			break;

		default:
			mes="No existe el usuario o el formato de fecha es invalida. Debe ser de la forma : dd/mm/aaa";
			break;
		}
		
		return mes;
	}
	

	public static void main(String[] args) {
		
		//Declaramos variables para definir nuestro constructor
		String codigos[] = new String[20];
		String nombres[] = new String[20];
		String fechas[] = new String[20];
		int edades[] = new int[20];
		char sexo[] = new char[20];
		int numHijos[] = new int[20];
		String direcciones[] = new String[20];
		
		//Simulacion de la Base de Datos
		codigos[0]="U001";
		codigos[1]="U002";
		codigos[2]="U003";
		codigos[3]="U004";
		codigos[4]="U005";
		codigos[5]="U006";
		codigos[6]="U007";
		codigos[7]="U008";
		codigos[8]="U009";
		codigos[9]="U010";
		codigos[10]="U011";
		codigos[11]="U012";
		codigos[12]="U013";
		codigos[13]="U014";
		codigos[14]="U015";
		codigos[15]="U016";
		codigos[16]="U017";
		codigos[17]="U018";
		codigos[18]="U019";
		codigos[19]="U020";
		
		nombres[0]="HERNANDEZ JUAREZ ANGIE";
		nombres[1]="JOSE ANTONIO MARTINEZ";
		nombres[2]="MAK VAZ JOSEFINA";
		nombres[3]="CRUZ MARTINEZ ELISEA";
		nombres[4]="CRUZ  JOSE LUPE";
		nombres[5]="RAMZES HERNANDEZ PEDROSA";
		nombres[6]="TORRES JUANA LIZ";
		nombres[7]="SANCHEZ LIA KAREN";
		nombres[8]="VALDEZ  SANTES PACO";
		nombres[9]="RAM HER DOROTEO";
		nombres[10]="CRUZ DOM FLOR";
		nombres[11]="HER SANC CASIMIRO";
		nombres[12]="JUAREZ LOPEZ GUSTAVO";
		nombres[13]="MALPICA OLARTE RUBEN";
		nombres[14]="JIMENEZ JUAREZ GABRIEL";
		nombres[15]="SOTO OLARTE ANGEL";
		nombres[16]="PEREZ SUGEY MARTINA";
		nombres[17]="RAMIREZ SANCHEZ ELOY";
		nombres[18]="RAMIREZ SANTA CRUZ  ANA";
		nombres[19]="RAMIREZ SARMIENTO PEDRO";
		
		fechas[0]="13/08/2002";
		fechas[1]="01/07/2000";
		fechas[2]="18/12/1991";
		fechas[3]="14/07/1989";
		fechas[4]="18/12/2000";
		fechas[5]="15/08/1999";
		fechas[6]="15/08/2002";
		fechas[7]="18/09/2002";
		fechas[8]="16/01/2002";
		fechas[9]="14/12/2000";
		fechas[10]="13/07/2001";
		fechas[11]="13/05/2001";
		fechas[12]="15/06/2001";
		fechas[13]="19/02/2001";
		fechas[14]="08/06/1986";
		fechas[15]="07/06/1985";
		fechas[16]="14/07/1989";
		fechas[17]="15/12/1990";
		fechas[18]="13/07/1987";
		fechas[19]="05/06/1983";
		
		edades[0] = 19;
		edades[1] = 21;
		edades[2] = 30;
		edades[3] = 32;
		edades[4] = 21;
		edades[5] = 22;
		edades[6] = 19;
		edades[7] = 19;
		edades[8] = 19;
		edades[9] = 21;
		edades[10] = 20;
		edades[11] = 20;
		edades[12] = 20;
		edades[13] = 20;
		edades[14] = 35;
		edades[15] = 36;
		edades[16] = 32;
		edades[17] = 31;
		edades[18] = 34;
		edades[19] = 38;
		
		sexo[0] = 'M';
		sexo[1] = 'M';
		sexo[2] = 'M';
		sexo[3] = 'M';
		sexo[4] = 'M';
		sexo[5] = 'H';
		sexo[6] = 'M';
		sexo[7] = 'M';
		sexo[8] = 'H';
		sexo[9] = 'H';
		sexo[10] = 'M';
		sexo[11] = 'H';
		sexo[12] = 'H';
		sexo[13] = 'H';
		sexo[14] = 'H';
		sexo[15] = 'H';
		sexo[16] = 'M';
		sexo[17] = 'H';
		sexo[18] = 'M';
		sexo[19] = 'M';
		
		numHijos[0]= 1;
		numHijos[1]= 2;
		numHijos[2]= 3;
		numHijos[3]= 4;
		numHijos[4]= 0;
		numHijos[5]= 0;
		numHijos[6]= 1;
		numHijos[7]= 0;
		numHijos[8]= 0;
		numHijos[9]= 0;
		numHijos[10]= 0;
		numHijos[11]= 1;
		numHijos[12]= 1;
		numHijos[13]= 2;
		numHijos[14]= 3;
		numHijos[15]= 3;
		numHijos[16]= 2;
		numHijos[17]= 0;
		numHijos[18]= 2;
		numHijos[19]= 3;
		
		direcciones[0]="Mz A lt 15 los granados";
		direcciones[1]="Jr. Las Nebulosas 2639";
		direcciones[2]="Jr. Los Opalos 2583";
		direcciones[3]="S/V Aahh San Fernando Mz F Lt 6";
		direcciones[4]="Urb. Jardines De Naranjal Mz E Lt 0";
		direcciones[5]="Av. Los Olivos Mz A Lt 04";
		direcciones[6]="Ca. Cinco Mz Y Lt 12";
		direcciones[7]="Ca. Cuatro Mz D Lt 20";
		direcciones[8]="Mz e lt 17 mayora,go 2 etapa";
		direcciones[9]="Asoc. Viv El Mirador I Mz D Lt 5";
		direcciones[10]="Asoc. Viv El Mirador I Mz D Lt 5";
		direcciones[11]="Virgen De La Puerta Mz A Lt 11";
		direcciones[12]="Urb. San Valentin Mz C Lt 07";
		direcciones[13]="Urb. Praderas De Naranjal Mz A Lt 0";
		direcciones[14]="Aa.hh. Ignacio Prado Mz D1 Lt 09";
		direcciones[15]="Aa.hh. Mariano Ignacio Prado Mz A L";
		direcciones[16]="Aa.hh. Ampliacion La Ensenada Mz R";
		direcciones[17]="Asoc. Asoc Chillon 5 Mz Q Lt 06";
		direcciones[18]="Aa.hh. Chillon Mz 7 Lt 6";
		direcciones[19]="Virgen De La Candelaria Mz A Lt 11";

		Scanner sc = new Scanner(System.in);
		
		//Instanciamos el objeto de tipo NominaUsuarios
		NominaUsuarios nom = new NominaUsuarios(codigos,nombres,fechas,edades,sexo,numHijos,direcciones);
		
		// Solicitamos el llenado de horas para cada operacion por cada tipo de prenda
		System.out.println("Ingrese el numero de tipo de operacion a realizar en la nomina :\n" +
                "1. Obtener datos de un Usuario\n" +
                "2. Cantidad de Varones de la nomina\n" +
                "3. Cantidad de Mujeres de la nomina\n" +
                "4. Cantidad de personas menores, igual o mayores a una edad dada\n" +
                "5. Promedio de edades de la nomina\n" +
                "6. Numero de usuarios con cantidad de hijos menores, igual o mayores a un numero dado\n" +
                "7. Promedio de numero de hijos de la nomina\n" +
                "8. Mes de cumpleaños");
		int opc = sc.nextInt();
		
		switch (opc) {
		case 1:
			System.out.println("Introducir codigo de Usuario (U0xx): ");
			sc.nextLine();
			String codigo=sc.nextLine();
			System.out.println(nom.devolverDatos(codigo));
			break;
		case 2:
			System.out.println(nom.cantidadVarones());
			break;
		case 3:
			System.out.println(nom.cantidadMujeres());
			break;
		case 4:
			System.out.println("Introducir una edad: ");
			int edad = sc.nextInt();
			System.out.println(nom.numPersonasEdad(edad));
			break;
		case 5:
			System.out.println(nom.promedioEdades());
			break;
		case 6:
			System.out.println("Introduce un numero de hijos : ");
			int num = sc.nextInt();
			System.out.println(nom.numCantidadHijos(num));
			break;
		case 7:
			System.out.println(nom.promedioCantidadHijos());
			break;
		case 8:
			System.out.println("Introducir codigo de Usuario (U0xx): ");
			sc.nextLine();
			String cumple=sc.nextLine();
			System.out.println(nom.mesCumpleaños(cumple));
			break;

		default:
			break;
		}	

	}

}
