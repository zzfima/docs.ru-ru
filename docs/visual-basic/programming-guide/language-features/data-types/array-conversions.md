---
title: Преобразование массивов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: a179b7cf5b82132db88fb5412f0ca4be207f0987
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="array-conversions-visual-basic"></a>Преобразование массивов (Visual Basic)
Тип массива можно преобразовать в другой тип массива при соблюдении следующих условий:  
  
-   **Равенство ранга.** Ранги двух массивов должны быть одинаковыми, то есть они должны иметь одинаковое число измерений. Однако длины соответствующих измерений не обязательно должны быть одинаковыми.  
  
-   **Тип данных элемента.** Типы данных элементов обоих массивов должны быть ссылочными типами. Не удается преобразовать `Integer` массив `Long` или даже к `Object` массива, так как тип по крайней мере одно значение. Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Возможность преобразования.** Необходимо, расширяющее или сужающее преобразование между типами элементов двух массивов. Пример, который не соответствует этим требованиям — попытка преобразования между `String` массива и массив класса, производного от <xref:System.Attribute?displayProperty=nameWithType>. Эти два типа не имеют ничего общего, и преобразование любого типа, не существует между ними.  
  
 Преобразование одного типа массива в другой расширяющее или сужающее в зависимости от ли расширяющее или сужающее преобразование соответствующих элементов. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Преобразование в массив объектов  
 При объявлении `Object` массив без инициализации, его тип элемента — `Object` до тех пор, пока он не будет инициализирован. При установке в массив определенного класса, он принимает тип этого класса. Однако его базовому типу по-прежнему `Object`, и можно позднее задать для него значение массива несвязанного класса. Поскольку все классы являются производными от `Object`, можно изменить тип элемента массива из любого класса для любого другого класса.  
  
 В следующем примере, не существует преобразования между типами `student` и `String`, но оба является производным от `Object`, поэтому все присвоения являются допустимыми.  
  
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
  
### <a name="underlying-type-of-an-array"></a>Базовый тип массива  
 Если изначально объявить массив с определенным классом, что класс является его базовый тип элемента. Если в дальнейшем массив другого класса, необходимо выполнить преобразование между двумя классами.  
  
 В следующем примере `students` — `student` массива. Так как не существует преобразования между `String` и `student`, последний оператор завершается с ошибкой.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Как: преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
