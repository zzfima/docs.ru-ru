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
ms.openlocfilehash: f69ed6e0040f33f810d324a76859d448e9dc7632
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601140"
---
# <a name="array-conversions-visual-basic"></a>Преобразование массивов (Visual Basic)
Тип массива можно преобразовать в другой тип массива при соблюдении следующих условий:  
  
- **Равенство ранга.** Ранги двух массивов должны быть одинаковыми, то есть они должны иметь одинаковое количество измерений. Однако длины соответствующих измерений не обязательно должны быть одинаковыми.  
  
- **Тип данных элемента.** Типы данных элементов обоих массивов должны быть ссылочными типами. Не удается преобразовать `Integer` массив `Long` или даже для `Object` массива, так как тип по крайней мере одно значение. Для получения дополнительной информации см. [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
- **Возможность преобразования.** Расширяющее или сужающее преобразование должно быть возможно между типами элементов двух массивов. Например, не соответствует этим требованиям, попытка преобразования между `String` массива, а также массив класс производным от <xref:System.Attribute?displayProperty=nameWithType>. Эти два типа не имеют ничего общего и преобразование любого типа не существует между ними.  
  
 Это преобразование одного типа массива в другой расширяющего или сужающего в зависимости от ли расширяющее или сужающее преобразование соответствующих элементов. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Преобразование в массив объектов  
 При объявлении `Object` массива без инициализации, его тип элемента — `Object` до тех пор, пока он не будет инициализирован. При установке его на массив определенного класса, он принимает тип этого класса. Тем не менее, его базовым типом является по-прежнему `Object`, и можно впоследствии разместить его в другой массив несвязанного класса. Так как все классы являются производными от `Object`, можно изменить тип элемента массива из любого класса к любому другому классу.  
  
 В следующем примере, не существует преобразования между типами `student` и `String`, но оба являются производными от `Object`, поэтому все назначения являются допустимыми.  
  
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
 Если изначально объявляется массив с определенным классом, его базовый тип элемента является этот класс. Если в дальнейшем массив другого класса, необходимо выполнить преобразование между двумя классами.  
  
 В следующем примере `students` является `student` массива. Так как не существует преобразования между `String` и `student`, последняя инструкция завершается неудачно.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
