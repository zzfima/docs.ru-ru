---
title: "Устранение неполадок, связанных с массивами (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "массивы [Visual Basic], ошибки компиляции"
  - "массивы [Visual Basic], объявление ошибок"
  - "массивы [Visual Basic], ошибки инициализации"
  - "массивы [Visual Basic], устранение неполадок"
  - "устранение неполадок, связанных с массивами"
  - "устранение неполадок - Visual Basic, массивы"
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Устранение неполадок, связанных с массивами (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

На этой странице перечислены некоторые общие проблемы, которые могут возникнуть при работе с массивами.  
  
## Ошибки компиляции при объявлении и инициализации массива  
 Ошибки компиляции могут возникать из\-за неправильной трактовки правил объявления, создания и инициализации массивов.  Наиболее часто встречаются следующие ошибки:  
  
-   Указание предложения [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) после указания размерностей при объявлении переменной массива.  Следующие строки кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Указание размерностей для массива не верхнего уровня в многомерном массиве.  Следующая строка кода показывает недопустимое объявление этого типа.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Пропуск ключевого слова `New` при указании значения элементов.  Следующая строка кода показывает недопустимое объявление этого типа.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Указание предложения `New` без фигурных скобок \(`{}`\).  Следующие строки кода показывают недопустимые объявления этого типа.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## Доступ к массиву за его пределами  
 Процесс инициализации массива назначает верхнюю и нижнюю границу каждому измерению.  При каждом доступе к элементу массива необходимо указывать допустимый индекс для каждого измерения.  Если любой индекс ниже его нижней границы или больше его верхней границы, то возникает исключение <xref:System.IndexOutOfRangeException>.  Компилятор не может обнаружить такую ошибку, поэтому она возникает во время выполнения.  
  
### Определение границ  
 Если другой компонент передает массив в код \(например в качестве аргумента процедуры\) размер массива или длина его измерений неизвестна.  Следует всегда определять верхнюю границу для каждого измерения массива до попытки получения доступа к какому\-либо элементу.  Если массив был создан с помощью некоторых средств, отличных от [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предложений `New`, то нижняя граница может быть отлична от 0, и лучше всего также определить и нижнюю границу.  
  
### Указание измерения  
 При определении границ многомерного массива следите за указанием измерения.  Параметры `dimension` методов <xref:System.Array.GetLowerBound%2A> и <xref:System.Array.GetUpperBound%2A> отсчитываются от 0, а параметры `Rank` функций <xref:Microsoft.VisualBasic.Information.LBound%2A> и <xref:Microsoft.VisualBasic.Information.UBound%2A> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] — от 1.  
  
## См. также  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Практическое руководство. Инициализация переменной массива в Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)