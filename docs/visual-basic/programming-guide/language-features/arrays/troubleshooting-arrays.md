---
title: "Устранение неполадок с массивами (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: db38c0c2a4f8b74a6b862f86f426b4d8837f4424
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-arrays-visual-basic"></a>Устранение неполадок, связанных с массивами (Visual Basic)
На этой странице перечислены некоторые общие проблемы, которые могут возникнуть при работе с массивами.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Ошибки компиляции, объявления и инициализации массива  
 Ошибки компиляции могут возникать из недопонимания правил для объявления, создания и инициализации массивов. Далее перечислены наиболее распространенные причины ошибки:  
  
-   Предоставление [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) предложение после указания размерностей при объявлении переменной массива. Следующие строки кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Указание размерностей для более чем массива верхнего уровня массива массивов. Следующая строка кода показывает недопустимое объявление этого типа.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Пропуск `New` ключевое слово, при указании значения элементов. Следующая строка кода показывает недопустимое объявление этого типа.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Предоставление `New` предложение без фигурных скобок (`{}`). Следующие строки кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Доступ к массиву за пределы допустимого диапазона  
 Процесс инициализации массива назначает верхнюю и нижнюю границу для каждого измерения. У каждого доступа к элементу массива необходимо указать допустимый индекс или индекс для любой размерности. Если индекс является ниже его нижней границы или выше верхней границы, <xref:System.IndexOutOfRangeException>Результаты исключения.</xref:System.IndexOutOfRangeException> Компилятор не обнаруживает такую ошибку, поэтому она возникает во время выполнения.  
  
### <a name="determining-bounds"></a>Определение границ  
 Если другой компонент передает массив в код, например в качестве аргумента процедуры неизвестно размер массива или длина его измерений. Следует всегда определять верхнюю границу для каждого измерения массива до попытки получить доступ все элементы. Если массив был создан с помощью некоторых средств не [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` предложение, нижняя граница может быть отлична от 0, и лучше всего определить, что нижняя граница.  
  
### <a name="specifying-the-dimension"></a>Указание измерения  
 При определении границ многомерного массива, будьте внимательны, как указать измерения. `dimension` Параметры <xref:System.Array.GetLowerBound%2A>и <xref:System.Array.GetUpperBound%2A>методов ведется от нуля, при `Rank` параметры [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A>и <xref:Microsoft.VisualBasic.Information.UBound%2A>функции основаны на 1.</xref:Microsoft.VisualBasic.Information.UBound%2A> </xref:Microsoft.VisualBasic.Information.LBound%2A> </xref:System.Array.GetUpperBound%2A> </xref:System.Array.GetLowerBound%2A>  
  
## <a name="see-also"></a>См. также  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Практическое руководство: инициализация переменной массива в Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
