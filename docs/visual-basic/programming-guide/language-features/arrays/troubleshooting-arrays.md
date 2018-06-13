---
title: Устранение неполадок, связанных с массивами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 4ab6d376ad8652e460e33c4f2c3285e8c80286fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654272"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Устранение неполадок, связанных с массивами (Visual Basic)
Этой странице перечислены некоторые общие проблемы, которые могут возникнуть при работе с массивами.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Ошибки компиляции, объявления и инициализации массива  
 Ошибки компиляции могут возникать из касающаяся правил для объявления, создания и инициализации массивов. Ниже перечислены наиболее распространенные причины ошибок:  
  
-   Предоставление [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) предложение после указания размерностей при объявлении переменной массива. В следующих строках кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Указание длины по измерениям дольше, чем массива верхнего уровня массива массивов. Следующая строка кода показывает недопустимое объявление этого типа.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Пропуск `New` ключевое слово, при указании значения элементов. Следующая строка кода показывает недопустимое объявление этого типа.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Предоставление `New` предложение без фигурных скобок (`{}`). В следующих строках кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Доступ к массиву за пределы допустимого диапазона  
 Процесс инициализации массива назначает верхнюю и нижнюю границу для каждого измерения. У каждого доступа к элементу массива необходимо указать допустимый индекс или индекс для любой размерности. Если индекс меньше его нижней границы или выше верхней границы, <xref:System.IndexOutOfRangeException> результаты исключения. Компилятор не может обнаружить такую ошибку, поэтому во время выполнения возникает ошибка.  
  
### <a name="determining-bounds"></a>Определение границ  
 Если другой компонент передает массив в коде, например в качестве аргумента процедуры, вы не знаете размер массива или длина его измерений. Всегда следует определить верхнюю границу для каждого измерения массива, прежде чем пытаться получить доступ к какие-либо элементы. Если массив был создан с помощью некоторых средств, отличных от Visual Basic `New` предложения, нижняя граница может быть нечто, отличное от 0 и безопаснее определить, что нижняя граница.  
  
### <a name="specifying-the-dimension"></a>Указание измерения  
 При определении границ многомерного массива, будьте внимательны, как указать измерения. `dimension` Параметры <xref:System.Array.GetLowerBound%2A> и <xref:System.Array.GetUpperBound%2A> методов начинаются с 0, при `Rank` параметры Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> и <xref:Microsoft.VisualBasic.Information.UBound%2A> функции основаны на 1.  
  
## <a name="see-also"></a>См. также  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Практическое руководство. Инициализация переменной массива в Visual Basic)
