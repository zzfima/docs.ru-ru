---
title: "Массивы параметров (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "аргументы [Visual Basic], массивы параметров"
  - "массивы [Visual Basic], массивы параметров"
  - "ParamArray - ключевое слово, массивы параметров"
  - "массивы параметров, сведения о массивах параметров"
  - "параметры, массивы параметров"
  - "процедуры, определение числа значений аргументов"
  - "код Visual Basic, процедуры"
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Массивы параметров (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Обычно в вызове процедуры не может быть больше аргументов, чем в ее объявлении.  Если точное число аргументов, которые предстоит использовать, неизвестно, то можно объявить *массив параметров*, который позволяет процедуре принять в качестве параметра массив значений.  При определении процедуры необязательно указывать количество элементов в массиве параметров.  Размер массива определяется заново при каждом вызове процедуры.  
  
## Объявление ParamArray  
 Ключевое слово [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) используется для обозначения массива параметров в списке параметров.  Действуют следующие правила.  
  
-   Процедура может определять только один массив параметров, и он должен быть последним параметром в определении процедуры.  
  
-   Массив параметров должен передаваться по значению.  Рекомендуется включать явным образом ключевое слово [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) в определение процедуры.  
  
-   Массив параметров всегда является необязательным.  По умолчанию его значением является пустой одномерный массив с заданным для массива параметров типом элемента массива.  
  
-   Все параметры, предшествующие в списке массиву параметров, должны быть обязательными.  Массив параметров должен быть единственным опциональным параметром.  
  
## Вызов ParamArray  
 При вызове процедуры, определяющей массив параметров, можно указать аргумент одним из следующих способов:  
  
-   Ничего, т.е. опустить аргумент [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md).  В этом случае процедуре передается пустой массив.  Такой же результат дает использование ключевого слова [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
-   Список из неопределенного числа аргументов, разделенных запятыми.  Тип данных каждого из аргументов должен неявным образом преобразовываться в тип элемента `ParamArray`.  
  
-   Массив с элементами того же типа, что и в массиве параметров.  
  
 Во всех случаях код в процедуре должен обрабатывать массив параметров как одномерный массив, каждый элемент которого имеет тот же тип данных, что и `ParamArray`.  
  
> [!IMPORTANT]
>  При работе с неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения.  Если принимается массив параметров, то следует проверить размер массива, переданного вызывающим кодом.  Предпринять соответствующие действия, если он слишком велик для приложения.  Дополнительные сведения см. в разделе [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Пример  
 В следующем примере определяется и вызывается функция `calcSum`.  Модификатор `ParamArray` для параметра `args` позволяет функции принять переменное число аргументов.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 Следующий пример определяет процедуру с массивом параметров и выводит значения всех элементов массива, переданных массиву параметров.  
  
 [!code-vb[VbVbcnProcedures#48](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Передача аргументов по позиции и по имени](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Необязательные параметры](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)