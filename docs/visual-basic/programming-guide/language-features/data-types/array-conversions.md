---
title: Преобразования массивов
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
ms.openlocfilehash: 622ebe8a77f2dfbeb35e0408be48622d93d409c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345863"
---
# <a name="array-conversions-visual-basic"></a>Преобразование массивов (Visual Basic)
Тип массива можно преобразовать в другой тип массива при условии соблюдения следующих условий.  
  
- **Равный ранг.** Ранги двух массивов должны быть одинаковыми, то есть они должны иметь одинаковое количество измерений. Однако длины соответствующих измерений не обязательно должны совпадать.  
  
- **Тип данных элемента.** Типы данных элементов обоих массивов должны быть ссылочными типами. Невозможно преобразовать массив `Integer` в массив `Long` или даже в массив `Object`, так как задействован хотя бы один тип значений. Для получения дополнительной информации см. [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
- **Вариантное.** Преобразование (расширяющее или сужение) должно быть возможным между типами элементов двух массивов. Пример, в котором не выполняется это требование — попытка преобразования между `String` массивом и массивом класса, производного от <xref:System.Attribute?displayProperty=nameWithType>. Эти два типа не имеют ничего общего, и между ними не существует каких либо преобразований.  
  
 Преобразование одного типа массива в другой может расширяться или уменьшаться в зависимости от того, является ли преобразование соответствующих элементов расширяющим или узким. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Преобразование в массив объектов  
 При объявлении массива `Object` без инициализации его тип элемента `Object`, пока он остается неинициализированным. При присвоении значения массиву определенного класса он принимает тип этого класса. Однако его базовый тип по-прежнему `Object`, и впоследствии его можно установить в другой массив несвязанного класса. Поскольку все классы являются производными от `Object`, можно изменить тип элемента массива с любого класса на любой другой класс.  
  
 В следующем примере преобразование между типами `student` и `String`не существует, но оба типа являются производными от `Object`, поэтому все назначения являются допустимыми.  
  
```vb  
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
 Если изначально был объявлен массив с конкретным классом, его базовым типом элемента является этот класс. Если впоследствии задать для него массив другого класса, необходимо выполнить преобразование между двумя классами.  
  
 В следующем примере `students` является массивом `student`. Поскольку преобразование между `String` и `student`не существует, последняя инструкция завершается ошибкой.  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Преобразования значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Как преобразовать объект в другой тип в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
