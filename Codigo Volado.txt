#!/usr/bin/perl
 #Elaborado por Marcelino Jorge Villarreal Leal
 #De la Facultad de Ingenieria Mecanica y Electrica
 #De la Universidad Autonoma de Nuevo Leon.
INICIO: print"\t Volado \n";
do { 
print"Selecciona si quieres que se haga por:\n 
1=numero de corridas o 2=por numero aleatorio... :";
chomp ($op = <>); 
while($op !=1 && $op!=2) {print"Esa opcion no existe.\n\n Vuelve a intentando:"; chomp ($op = <>);}

if ($op == 1) {
Corridas:
S: print"Bien, selecciona el numero de Corridas Maximo: ";
chomp ($Co = <>); if($Co<0) {print"Esa opcion no existe.\n\n Vuelve a intentando\n"; goto S}
print"Cantidad inicial: \$";
chomp ($X = <>); print"X= $X \n";
M: print"Meta: \$";
chomp ($M = <>); print"M= $M \n"; if($M < $X) { print" la meta no puede ser menor a lo que tienes intenta de nuevo \n"; goto M}
L: print"Apuesta Inicial: \$";
chomp ($APi = <>); print"APi= $APi \n"; if($APi > $X) { print" la apuesta no puede ser mayor a lo que tienes intenta de nuevo \n"; goto L}
print"La apuesta inicial es de $APi, si se pierde se apuesta \$2($APi) y asi sucesivamente\n";
print"Se gana el volado cuando el numero aleatorio es menor o igual a 0.5 Y se pierde cuando es mayor a este\n";
print"Cual es la probabilidad de llegar a la meta?, Cuantas veces se llego
a la meta? y cuantas a la quiebra?\n\n";
print"Para iniciar  programa presiona cualquier tecla...";
chomp ($In = <>);
#NC=numero de corrida CADV=Cantidad antes de volado APi=ApuestaInical $APA=ApuestaAcumulada 
#$VOL= se gano el volado? $CDDV Cantidad despues del volado $Met=se llego a la meta?  
$NC = 1;
$CADV = $X;
$CDDV = 0;
$APA = $APi;
$Vuelta = 1;
$Quiebra = 0;
$Met = 0;
$Q = 0;
while ($Co >= $NC){ 
print"numero de corrida:$NC \n "; 
print"Cantidad antes de volado:$CADV \n "; 
print"Apuesta:$APA \n "; $rand= (rand);
print"Numero rectangular:$rand \n ";
print"Se gano el volado? \n ";
if($rand <= 0.50000000000000) {
print"Si \n ";
$CDDV = $CADV+$APA;
$APA = $APi;
$Vuelta =1;
print"Cantidad despues del volado:$CDDV \n";
}
else{print"No \n "; 
$CDDV = $CADV-$APA;
++$Vuelta;
$APA+=$APi;
print"$APA";
print"Cantidad despues del volado:$CDDV \n";}
print"Se llego a la meta?\n ";
if ($CDDV>=$M) { print" Meta \n"; $Met++; 
}
elsif ($CDDV<=$Quiebra){print "Quiebra\n"; $Q++}else{print"No \n";} 
$CADV = $CDDV; 
if ($CDDV>=$M or $CDDV<=$quiebra){ $NC++; $Vuelta =1; $CDDV = 0; $CADV = $X;}
}
print"\n Numero de veces de llegada a la Meta: #$Met \n ";
print"Numero de veces de llegada a la Quiebra #$Q \n ";  $O=100;
print"Numero de Corridas : #$Co \n ";   
$PLLM= ($Met/$Co)*100; $PLLQ= ($Q/$Co)*100; 
print"Probabilidad de lleagar a la Meta: %$PLLM \n "; 
print"Probabilidad de lleagar a la Quiebra: %$PLLQ \n ";
print "\n \n \t Presione 1 si quiere volver a iniciar el programa y 2 para salir: \n " ;
chomp ($op = <>); 
while($op !=1 && $op!=2) {print"Esa opcion no existe.\n\n Vuelve a intentando:"; chomp ($op = <>);}
if ($op == 1) { system("cls"); goto INICIO} elsif ($op == 2) {system("cls"); print "ADIOS"; exit; }
}

if ($op == 2) { 
Aleatorios: 
V: print"Bien, selecciona el numero de Numeros aleatorios a generar:";
chomp ($Al = <>); if($Co<0) {print"Esa opcion no existe.\n\n Vuelve a intentando\n"; goto V}
print"Cantidad inicial: \$";
chomp ($X = <>); print"X= $X \n";
N: print"Meta: \$";
chomp ($M = <>); print"M= $M \n"; if($M < $X) { print" la meta no puede ser menor a lo que tienes intenta de nuevo \n"; goto N}
K: print"Apuesta Inicial: \$"; 
chomp ($APi = <>); print"APi= $APi \n"; if($APi > $X) { print" la apuesta no puede ser mayor a lo que tienes intenta de nuevo \n"; goto K}
print"La apuesta inicial es de $APi, si se pierde se apuesta \$2($APi) y asi sucesivamente\n";
print"Se gana el volado cuando el numero aleatorio es menor o igual a 0.5 Y se pierde cuando es mayor a este\n";
print"Cual es la probabilidad de llegar a la meta?, Cuantas veces se llego
a la meta? y cuantas a la quiebra?\n\n";
print"Para iniciar  programa presiona cualquier tecla...";
chomp ($In = <>);
#NC=numero de corrida CADV=Cantidad antes de volado APi=ApuestaInical $APA=ApuestaAcumulada 
#$VOL= se gano el volado? $CDDV Cantidad despues del volado $Met=se llego a la meta?  
$NC = 1;
$CADV = $X;
$CDDV = 0;
$APA = $APi;
$Vuelta = 1;
$Quiebra = 0;
$Met = 0;
$Q = 0;
$A = 0;
while ($Al >= $A){ 
print"numero de corrida:$NC \n "; 
print"Cantidad antes de volado:$CADV \n "; 
print"Apuesta:$APA \n "; $rand= (rand);
print"Numero rectangular #$A:$rand \n ";
print"Se gano el volado? \n ";
if($rand <= 0.50000000000000) {
print"Si \n ";
$CDDV = $CADV+$APA;
$APA = $APi;
$Vuelta =1;
print"Cantidad despues del volado:$CDDV \n";
}
else{print"No \n "; 
$CDDV = $CADV-$APA;
++$Vuelta;
$APA+=$APi;
print"$APA";
print"Cantidad despues del volado:$CDDV \n";}
print"Se llego a la meta?\n ";
if ($CDDV>=$M) { print" Meta \n"; $Met++; 
}
elsif ($CDDV<=$Quiebra){print "Quiebra\n"; $Q++}else{print"No \n";} 
$CADV = $CDDV; 
if ($CDDV>=$M or $CDDV<=$quiebra){ $NC++; $Vuelta =1; $CDDV = 0; $CADV = $X;}
$A++; 
#fin de la op 2
}
print"\n Numero de veces de llegada a la Meta: #$Met \n ";
print"Numero de veces de llegada a la Quiebra #$Q \n ";  $O=100;
print"Numero de Corridas : #$NC \n ";   
$PLLM= ($Met/$NC)*100; $PLLQ= ($Q/$NC)*100; 
print"Probabilidad de lleagar a la Meta: %$PLLM \n "; 
print"Probabilidad de lleagar a la Quiebra: %$PLLQ \n ";

print "\n \n \t Presione 1 si quiere volver a iniciar el programa y 2 para salir: \n " ;
chomp ($op = <>); 
while($op !=1 && $op!=2) {print"Esa opcion no existe.\n\n Vuelve a intentando:"; chomp ($op = <>);}
if ($op == 1) { system("cls"); goto INICIO} elsif ($op == 2) {system("cls"); print "ADIOS"; exit; }
}

#fin del do
}
