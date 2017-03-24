---
title: "Преобразование массивов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "массивы [Visual Basic], преобразование типа"
  - "массивы [Visual Basic], типы данных"
  - "преобразования, типы массивов"
  - "преобразования, тип данных"
  - "преобразования, тип"
  - "преобразование типов данных, преобразования массивов"
  - "массивы объектов"
  - "массивы объектов, преобразование типа"
  - "преобразование типов, массивы"
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Преобразование массивов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Тип массива можно преобразовать в другой тип при соблюдении следующих условий:  
  
-   **Равенство ранга.** Ранги двух массивов должны быть одинаковы, т.е. они должны иметь одинаковое количество размерностей.  В то же время длины соответствующих измерений не обязательно должны совпадать.  
  
-   **Тип данных элемента.** Типы данных элементов обоих массивов должны быть ссылочными типами.  Нельзя преобразовать массив `Integer` в массив `Long` или даже в массив `Object`, так как в нем содержится по крайней мере один тип значения.  Дополнительные сведения см. в разделе [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Возможность преобразования.** Преобразование между типами элементов двух массивов возможно как расширяющее, так и сужающее.  Пример, который не соответствует этим требованиям — попытка преобразования между массивом `String` и массивом класса, производного от <xref:System.Attribute?displayProperty=fullName>.  Эти два типа не имеют ничего общего, и для них не существует преобразования.  
  
 Преобразование одного типа массива в другой является расширяющим или сужающим в зависимости от того, расширяющими или сужающими являются преобразования соответствующих элементов.  Дополнительные сведения см. в разделе [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## Преобразование в массив Object  
 Если массив `Object` объявлен без инициализации, типом его элементов является `Object` до тех пор, пока он не будет инициализирован.  Когда для него задается значение массива определенного класса, он принимает тип этого класса.  Однако `Object` остается базовым типом, и можно позднее задать для него значение массива несвязанного класса.  Так как все классы являются производными от `Object`, можно изменять типы элементов массива одного класса на типы любого другого класса.  
  
 В следующем примере между типами `student` и `String` не существует преобразования, но оба является производными от `Object`, поэтому все присвоения являются допустимыми.  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### Базовый тип массива  
 Если изначально был объявлен массив определенного класса, то базовым типом элемента является этот класс.  Если в дальнейшем класс массива изменяется, необходимо выполнить преобразование между двумя классами.  
  
 В следующем примере `students` является массивом `student`.  Так как преобразование между `String` и `student` не существует, последний оператор завершается с ошибкой.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Преобразование значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)