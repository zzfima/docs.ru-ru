---
title: "Массивы параметров (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ca2b5f02ac4fb3eb613488c8a9852eb2aa4ce5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-arrays-visual-basic"></a>Массивы параметров (Visual Basic)
Как правило не может вызвать процедуру с большим числом аргументов, чем в объявлении процедуры указано. Если неопределенное число аргументов, можно объявить *массив параметров*, который позволяет процедуре принять массив значений для параметра. Необходимо знать количество элементов в массиве параметров, при определении процедуры. Размер массива определяется отдельно при каждом вызове процедуры.  
  
## <a name="declaring-a-paramarray"></a>Объявление ParamArray  
 Вы используете [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) ключевое слово для обозначения массива параметров в списке параметров. Действуют следующие правила.  
  
-   Процедура может определять только один массив параметров, и он должен быть последним параметром в определении процедуры.  
  
-   Массив параметров должен передаваться по значению. Это целесообразно, чтобы явно включить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ключевого слова в определении процедуры.  
  
-   Массив параметров автоматически является необязательным. Значением по умолчанию является пустой одномерный массив типа элемента в массиве параметров.  
  
-   Все аргументы, предшествующие в массиве параметров должны быть обязательными. Массив параметров должен быть единственным необязательным параметром.  
  
## <a name="calling-a-paramarray"></a>Вызов ParamArray  
 При вызове процедуры, определяющей массив параметров, можно указать аргумент одним из следующих способов:  
  
-   Nothing, то есть можно опустить [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) аргумент. В этом случае процедуре передается пустой массив. Можно также передать [ничего](../../../../visual-basic/language-reference/nothing.md) ключевое слово с такой же эффект.  
  
-   Список произвольное число аргументов, разделенных запятыми. Тип данных каждого аргумента должен быть неявно преобразовываться в `ParamArray` тип элемента.  
  
-   Массив с тем же типом элемента, что тип элемента в массиве параметров.  
  
 Во всех случаях код в процедуре рассматривает массив параметров как одномерный массив с элементами того же типа данных как `ParamArray` тип данных.  
  
> [!IMPORTANT]
>  При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения. Если вы принимаете массив параметров, следует проверить размер массива, которое передано вызывающему коду. Примите необходимые меры, если она слишком велика для приложения. Дополнительные сведения см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Пример  
 Следующий пример определяет и вызывает функцию `calcSum`. `ParamArray` Модификатор параметра `args` разрешает функции принимать переменное число аргументов.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 Следующий пример определяет процедуру с массивом параметров и выводит значения всех элементов массива, передаваемый в массиве параметров.  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)  
 [Необязательные параметры](./optional-parameters.md)  
 [Перегрузка процедур](./procedure-overloading.md)  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Необязательный](../../../../visual-basic/language-reference/modifiers/optional.md)
