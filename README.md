# dart240522
/*    
 TIPOS DE CLASES   
    normales
    abstractas
    mixin
*/

void imprimir(Personaje dummy, String msg){
  dummy.speak(msg);
}

void main() {
  Heroe spiderman = new Heroe();
  Antagonista venom = new Antagonista();
  Antagonista octopus = new Antagonista();
  Personaje whocare = Heroe(); //UpCasting 
//   spiderman.speak("spidy");
//   venom.speak("me gustan los cerebros");
//   octopus.speak("El poder es mio");
  imprimir(Heroe(),"Speedy");
  imprimir(Antagonista(),"CHACHACHAAAAU");
}

//convertir a clase abstracta
abstract class Personaje{
  final String? _alias = "dummy";
  final String? _power = "Resistencía";
  bool? _isNice = true;
  void speak(String msg);
  set isNice(bool nice){
    _isNice = nice;
  }
  String? msg = "Holi";
  String get message => msg;
}
/*
 Para usar todos los atributos y métodos de una clase se usa el implements.
 Si queremos hacer uso de la clase pero no de todos los metodos
 entonces utilizamos el Extends. Si sólo usarmeos un sólo método lo mejor es
 usar Mixin!
*/
abstract class Heroe with tec implements Personaje{
   bool? _isNice = true;
    @override
  void speak(String msg);
  print(msg);
  escabar();
@override
  set isNice(bool nice){
    isNice = nice;
  }
  String? msg;
  String get message => msg;
}
abstract class Antagonista extends Personaje{
    @override
  void speak(String msg);
  print(msg);
}

class tec{
  //MIXIN
    mixin Tech{
      void escabar(){
         print("holi");  
      }
    }
}
