---
title: "Типы данных параметров типа не могут быть определены из этих аргументов"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b290c25286dce2236823919e8287db9abefc0dd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a>Типы данных параметров типа не могут быть определены из этих аргументов
Типы данных параметров типа не могут выводиться из этих аргументов. Эту ошибку может исправить явное указание типов данных.  
  
 Эта ошибка возникает при неудачном разрешении перегрузки. Ошибка появляется в виде сообщения, в котором указывается, почему была исключена определенная потенциальная перегрузка. Сообщение об ошибке объясняется, компилятор не может использовать определение типа, чтобы найти типы данных для параметров типа.  
  
> [!NOTE]
>  Когда указание аргументов является обязательным (например, в операторах выражений запросов), это сообщение об ошибке появляется без второй фразы.  
  
 Эта ошибка демонстрируется в приведенном ниже коде.  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 **Идентификатор ошибки:** BC36647 и BC36644  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Попробуйте указать тип данных для параметра или параметров типа, вместо того чтобы полагаться на определение типа.  
  
## <a name="see-also"></a>См. также  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Универсальные процедуры в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
