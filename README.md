# ![Vista del módulo de cuotas](img/Logo.png)

 Gestión Económica - Subsistema de Administración Financiera de Fincas

> _Sistema para la automatización y control financiero de comunidades gestionadas por la empresa._

---

## :bookmark_tabs: Índice

- [:pencil2: Introducción](#wrench-introducción)
- [:open_file_folder: Funcionalidades del Subsistema](#package-funcionalidades-del-subsistema)
  - [:bar_chart: Gestión de recibos y cuotas](#receipt-gestión-de-recibos-y-cuotas)
  - [:incoming_envelope: Control de devoluciones](#repeat-control-de-devoluciones)
  - [:moneybag: Gestión de presupuestos comunitarios](#moneybag-gestión-de-presupuestos-comunitarios)
  - [:bar_chart: Informes y análisis financiero](#bar_chart-informes-y-análisis-financiero)
- [:straight_ruler: Estructura del Código](#bar_chart-estructura-del-código)
- [:books: Galería de Imágenes](#framed_picture-galería-de-imágenes)
- [:warning: Notificaciones y Alertas](#warning-notificaciones-y-alertas)
- [:busts_in_silhouette: Integrantes del Grupo](#busts_in_silhouette-integrantes-del-grupo)

---

## :pencil2: Introducción

El **Subsistema de Gestión Económica** tiene como objetivo centralizar y automatizar la administración de los aspectos financieros relacionados con las fincas y comunidades gestionadas por la empresa.

Este módulo permite:

- :receipt: Gestionar recibos, cuotas y pagos.
- :repeat: Controlar devoluciones y notificar automáticamente a los implicados.
- :moneybag: Crear y analizar presupuestos anuales y específicos.
- :bar_chart: Obtener informes económicos para la toma de decisiones estratégicas.

> :bulb: _Este subsistema se integra con los módulos de comunidades, propietarios, contratos y mantenimiento._

---

## :open_file_folder: Funcionalidades del Subsistema

### :bar_chart: Gestión de recibos y cuotas

- Registro y control de recibos periódicos (agua, luz, gas, etc.).
- Gestión de cuotas ordinarias y extraordinarias a propietarios.
- Estados de pago: pagado, pendiente, devuelto.
- Control del historial de pagos y fechas de abono por propietario.
- Información asociada a cuentas bancarias de las comunidades.
- Relación con empresas emisoras y contratos firmados.
- Emisión periódica automática de cuotas.

---

### :incoming_envelope: Control de devoluciones

- Registro de recibos devueltos (motivo, fecha, servicio).
- Registro de cuotas devueltas (motivo, fecha, propietario).
- Generación de informes de devoluciones.
- Notificaciones automáticas a propietarios y administrador.

---

### :moneybag: Gestión de presupuestos comunitarios

- Creación y gestión de presupuestos anuales por comunidad.
- Gestión de presupuestos específicos para incidencias imprevistas.
- Asociados a partidas presupuestarias (conceptos, tipo, importe estimado y real).
- Visualización de ingresos previstos y gastos estimados.

---

### :bar_chart: Informes y análisis financiero

- Informes mensuales/anuales por comunidad.
- Desglose de ingresos, gastos y saldo.
- Exportación de informes económicos para auditoría.

---

## :bar_chart: Estructura del Código

```java
//sara

public class Economia {
    protected int mes;
    protected String desc;
    protected double dinero;
    protected String estado;

    public Economia(){
        mes=0;
        desc=" ";
        dinero=0.0;
        estado=" ";
    }
  
  
    public Economia(int mes, double dinero){
        this.mes=mes;
        this.dinero=dinero;
    }


    public Economia( int mes, String desc, double dinero, String estado){
        this.mes=mes;
        this.desc=desc;
        this.dinero=dinero;
        this.estado=estado;
    }
}


import java.util.ArrayList;
import java.util.Scanner;

public class main {
    public static void main(String[] args){
        Scanner tec= new Scanner(System.in);
        //Sara
        ArrayList<Economia> recibo= new ArrayList<>();
        Recibo rec= new Recibo();

        int menu;
        boolean fin=true;

        do { 
            System.out.println("[0] Salir ");
            System.out.println("[1] Gestionar fincas");
            System.out.println("[2] Gestionar empresas de servicio ");
            System.out.println("[3] Gestionar incidencias  ");
            System.out.println("[4] Gestión económica ");
            menu=tec.nextInt();

            switch (menu) {
                case 1:
                    
                    break;
                case 2:
                    
                    break;
                case 3:
                    
                    break;
                case 4: //Sara
                    boolean finaleconomia=true;
                    int menueconomia;
                    do { 
                        
                        System.out.println("-----------------------------------");
                        System.out.println("Bienvenido a la gestión económica de tu finca, primero elige que quieres hacer"); 
                        System.out.println("[0] Volver atrás"); 
                        System.out.println("[1] Gestionar los recibos"); 
                        System.out.println("[2] Gestionar las devoluciones"); 
                        System.out.println("[3] Gestionar los gastos comunitarios"); 
                        System.out.println("-----------------------------------"); 
                        menueconomia=tec.nextInt();

                        switch (menueconomia) {
                            case 1:
                                boolean finreciv=true;
                                int recibmenu;

                                do {    
                                    System.out.println("[0] Volver");
                                    System.out.println("[1] Añadir un recibo");
                                    System.out.println("[2] Eliminar un recibo");
                                    System.out.println("[3] Consultar un recibo");
                                    recibmenu=tec.nextInt();

                                    switch (recibmenu) {
                                        case 1:

                                            int cod, mes;
                                            double dinero;

                                            System.out.println("Introduce el código del recibo");
                                            cod=tec.nextInt();
                                            System.out.println("Introduce el mes del recibo");
                                            mes=tec.nextInt(); 
                                            System.out.println("Introduce el dinero del recibo");
                                            dinero=tec.nextDouble();
                                            
                                            rec= new Recibo(cod, mes, dinero);
                                            recibo.add(rec);
                                            break;
                                        
                                        case 2:
                                            int elilmcod, aux;

                                            System.out.println("Introduce el código del recibo para eliminar");
                                            elilmcod=tec.nextInt();

                                            for (int i = 0; i < recibo.size(); i++) {
                                                recibo.get(i);
                                                aux=rec.getCod();
                                                if (aux==elilmcod) {
                                                    recibo.remove(i);
                                                    System.out.println("El recibo con cod "+aux+" se ha eliminado con éxito");
                                                }else
                                                    System.out.println("No se ha encontrado ese recibo");
                                            }
                                            break;
                                        
                                        case 3:
                                            int buscacod , encod;
                                            
                                            System.out.println("Estos son todos los recibos guardados hasta ahora: ");
                                            for (int i = 0; i < recibo.size(); i++) {
                                                System.out.println(recibo.get(i).toString());
                                            }
                                            break;
                                            
                                        default:
                                            finreciv=false;
                                    }     
                                } while (finreciv==true);
                                break;

                            case 2:
                                // igual que recibos 
                                break;
                            case 3:
                                // igual que recibos
                                break;
                            default:
                                finaleconomia=false;
                        }
                    } while (finaleconomia==true);
                





                    break;

                default:
                    System.out.println("Adiós");
                    fin=false;
            }
        } while (fin==true);
    }
}
```

---



## :warning: Notificaciones y Alertas

:white_check_mark: NOTIFICACIÓN: El recibo de Suministro de agua - Marzo ha sido pagado correctamente.

:warning: ADVERTENCIA: La cuota del propietario José Pérez se encuentra devuelta.

:x: ERROR: No ha sido posible generar el informe financiero por falta de conexión con la base de datos.

## :busts_in_silhouette: Integrantes del Grupo

Los integrantes del proyecto han sido:

- :bust_in_silhouette: Sara Gómez 
- :bust_in_silhouette: Genma
- :bust_in_silhouette: Isaac
- :bust_in_silhouette: Reina
- :bust_in_silhouette: Carlos

| Nombre     | Rol   | Subsistema             |
|------------|-------|------------------------|
| Sara       | Secretario | Gestión económica |
| Isaac      | Coordinador | Gestión empresa y servicios |
| Reina      | Portavoz | Gestión de incidencias |
| Carlos     | Facilitador | Gestión recursos humanos |

---

:link: [Volver al índice](#bookmark_tabs-índice)

[Repositorio del proyecto principal](https://github.com/drevi18/proyecto-intermodular)
