# Actividad-6.1

#1
#!/bin/bash
   echo "Introduce un número entero:"
   read num
   if [ $num -gt 0 ]
   then
   	echo "El número es positivo"
   fi

#2
#!/bin/bash
   echo "Introduce un número entero:"
   read num
   if [ $num -lt 0 ]
   then
   	echo "El número es negativo"
   fi

#3
#!/bin/bash
   echo "Introduce un número entero:"
   read num
   if [ $num -eq 0 ]
   then
   	echo "El número es igual a cero"
   fi

#4
#!/bin/bash
   echo "Introduce un número entero:"
   read num
   if [ $num -gt 0 ]
   then
   	echo "El número es positivo"
   elif [ $num -lt 0 ]
   then
   	echo "El número es negativo"
   else
   	echo "El número es igual a cero"
   fi

#5
#!/bin/bash
   if [ $# -eq 3 ]
   then
   	echo "El número de parámetros introducidos es correcto"
   else
   	echo "Error: el número de parámetros introducidos no es correcto"
   fi

#6
#!/bin/bash
if [ $# -ne 2 ]
then
   echo "Error: número de parámetros incorrecto."
else
   let suma=$1+$2
   echo "La suma es: $suma"
fi

#7
#!/bin/bash
if [ $# -ne 3 ]
then
   echo "Error: número de parámetros incorrecto."
else
   case $3 in
      "+") let result=$1+$2;;
      "-") let result=$1-$2;;
      "x") let result=$1\*$2;;
      "/") let result=$1/$2;;
      *) echo "Error: símbolo incorrecto. Las opciones son +, -, x o /." ;;
   esac
   echo "Resultado: $result"
fi

#8
#!/bin/bash
if [ $# -ne 1 ]
then
   echo "Error: número de parámetros incorrecto."
else
   if [ -f $1 ]
   then
      echo "El fichero existe."
   else
      echo "El fichero no existe."
   fi
fi

#9
#!/bin/bash
if [ $# -ne 1 ]
then
   echo "Error: número de parámetros incorrecto."
else
   if [ -d $1 ]
   then
      echo "Es un directorio."
   elif [ -f $1 ]
   then
      echo "Es un fichero."
   else
      echo "No es un directorio ni un fichero."
   fi
fi

#10 
#!/bin/bash
if [ $# -ne 1 ]
then
   echo "Error: número de parámetros incorrecto."
else
   if [ -f $1 ]
   then
      permisos=$(ls -l $1 | cut -d " " -f 1)
      echo "Permisos: $permisos"
   else
      echo "El fichero no existe."
   fi
fi


#11 
#!/bin/bash
for ((i=0;i<50;i++))
do
    echo "hola"
done

#12
#!/bin/bash
for ((i=0;i<10;i++))
do
    read -p "Ingresa una palabra: " palabra
    echo $palabra
done

#13
#!/bin/bash
num=$1
for ((i=0;i<$num;i++))
do
    echo "hola"
done

#14
#!/bin/bash
num=$1
for ((i=0;i<=$num;i++))
do
    echo $i
done

#15
#!/bin/bash
num=$1
suma=0
for ((i=1;i<=$num;i++))
do
    suma=$((suma + i))
done
echo "La suma es: $suma"

#16
#!/bin/bash

aux=$1
$1=$2
$2=$aux

#17
#!/bin/bash

while true; do
    read -p "Introduce una palabra: " word
    if [ "$word" == ":q" ]; then
        break
    fi
done

#18
#!/bin/bash

while true; do
    read -p "Introduce una palabra: " word
    if [ "$word" == ":q" ]; then
        break
    fi
    echo "$word" >> words.txt
done

#19
#!/bin/bash

sort -o words.txt words.txt
while true; do
    read -p "Introduce una palabra: " word
    if [ "$word" == ":q" ]; then
        break
    fi
    echo "$word" >> words.txt
    sort -o words.txt words.txt
done

#20
#!/bin/bash

read -p "Introduce un número: " num
if grep -q $num number.txt; then
    echo "El número $num se encuentra en el archivo."
else
    echo "El número $num no se encuentra en el archivo."
fi
