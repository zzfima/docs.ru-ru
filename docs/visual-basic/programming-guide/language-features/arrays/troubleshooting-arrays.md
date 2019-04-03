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
ms.openlocfilehash: 2b051d22fe3d331626f2e181c008043e576b7526
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833377"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Устранение неполадок, связанных с массивами (Visual Basic)
Этой странице перечислены некоторые распространенные проблемы, которые могут возникнуть при работе с массивами.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Ошибки компиляции, объявления и инициализации массива  
 Ошибки компиляции могут возникнуть с неправильным пониманием того, правила для объявления, создания и инициализации массивов. Ниже перечислены наиболее распространенные причины ошибок.  
  
-   Предоставление [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) предложение после указания размерностей в объявлении переменной массива. Следующие строки кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Указание длины по измерениям дольше, чем массива верхнего уровня массива массивов. В следующей строке кода показано недопустимое объявление этого типа.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Пропуск `New` ключевое слово, при указании значения элементов. В следующей строке кода показано недопустимое объявление этого типа.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Предоставление `New` предложение без фигурных скобок (`{}`). Следующие строки кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Доступ к массиву вне допустимых границ  
 Процесс инициализации массива назначает верхней и нижней границей каждого измерения. При каждом обращении к элемент массива необходимо указать допустимый индекс или индекс, для каждого измерения. Если любой индекс ниже его нижней границы или выше верхней границы, <xref:System.IndexOutOfRangeException> результаты исключения. Компилятор не обнаруживает такую ошибку, поэтому она возникает во время выполнения.  
  
### <a name="determining-bounds"></a>Определение границ  
 Если другой компонент передает массив в коде, например как аргумент процедуры, вы не знаете размер массива или длина его измерений. Всегда необходимо определить верхнюю границу для каждого измерения массива, прежде чем пытаться получить доступ к какие-либо элементы. Если массив был создан с помощью некоторых средств, отличных от Visual Basic `New` предложение, нижняя граница может быть что-то отличное от 0, и лучше всего определить, что нижняя граница.  
  
### <a name="specifying-the-dimension"></a>Указание измерения  
 При определении границ многомерного массива, будьте внимательны, как указать измерения. `dimension` Параметры <xref:System.Array.GetLowerBound%2A> и <xref:System.Array.GetUpperBound%2A> методов начинаются с нуля, при `Rank` параметры Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> и <xref:Microsoft.VisualBasic.Information.UBound%2A> функции начинаются с 1.  
  
## <a name="see-also"></a>См. также

- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Практическое руководство. Инициализация переменной массива в Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
