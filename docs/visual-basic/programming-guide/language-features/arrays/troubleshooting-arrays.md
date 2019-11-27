---
title: Устранение неполадок, связанных с массивами
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 3c50c68c2a39aa04cff2dd43b5dfde709aec290f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349068"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Устранение неполадок, связанных с массивами (Visual Basic)
На этой странице перечислены некоторые распространенные проблемы, которые могут возникнуть при работе с массивами.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Ошибки компиляции при объявлении и инициализации массива  
 Ошибки компиляции могут возникать из нечеткого понимания правил объявления, создания и инициализации массивов. Ниже перечислены наиболее распространенные причины возникновения ошибок.  
  
- Перед указанием длины измерения в объявлении переменной массива следует указать [новое предложение оператора](../../../../visual-basic/language-reference/operators/new-operator.md) . В следующих строках кода показаны недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- Задание длины измерений для большего массива массивов массивов. В следующей строке кода показано недопустимое объявление этого типа.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- Пропуск ключевого слова `New` при указании значений элементов. В следующей строке кода показано недопустимое объявление этого типа.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- Указание `New` предложения без фигурных скобок (`{}`). В следующих строках кода показаны недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Доступ к массиву вне границ  
 Процесс инициализации массива назначает верхнюю границу и нижнюю границу для каждого измерения. Каждый доступ к элементу массива должен указывать допустимый индекс (или подстрочный) для каждого измерения. Если какой-либо индекс находится ниже нижней границы или выше его верхней границы, <xref:System.IndexOutOfRangeException> результаты исключения. Компилятор не может обнаружить такую ошибку, поэтому во время выполнения возникает ошибка.  
  
### <a name="determining-bounds"></a>Определение границ  
 Если другой компонент передает массив в код, например в качестве аргумента процедуры, размер этого массива или длины его измерений неизвестн. Прежде чем пытаться получить доступ к любому элементу, необходимо всегда определять верхнюю границу для каждого измерения массива. Если массив был создан другими способами, отличными от предложения Visual Basic `New`, то нижняя граница может быть не равна 0, а также наиболее надежно определить нижнюю границу.  
  
### <a name="specifying-the-dimension"></a>Указание измерения  
 При определении границ многомерного массива следует соблюдать осторожность при указании измерения. Параметры `dimension` методов <xref:System.Array.GetLowerBound%2A> и <xref:System.Array.GetUpperBound%2A> равны 0, а параметры `Rank` Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> и <xref:Microsoft.VisualBasic.Information.UBound%2A> — от 1.  
  
## <a name="see-also"></a>См. также

- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Практическое руководство. Инициализация переменной массива в Visual Basic)
