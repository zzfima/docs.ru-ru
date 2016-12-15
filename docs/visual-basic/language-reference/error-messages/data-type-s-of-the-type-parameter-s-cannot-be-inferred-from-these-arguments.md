---
title: "Типы данных параметров-типов не могут быть определены из этих аргументов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36644"
  - "bc36647"
  - "vbc36647"
  - "vbc36644"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36644"
  - "BC36647"
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Типы данных параметров-типов не могут быть определены из этих аргументов
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Типы данных параметров\-типов не могут быть определены из этих аргументов.Явное указание типов данных может исправить эту ошибку.  
  
 Эта ошибка появляется при неудачном разрешении перегрузки.  При этом появляется подчиненное сообщение с информацией о том, почему был исключен конкретный кандидат на перегрузку.  В сообщении об ошибке объясняется, что компилятору не удается использовать определение типа, чтобы найти типы данных для параметров типа.  
  
> [!NOTE]
>  Когда аргументы являются обязательными \(например, в операторах запросов в выражениях запросов\), это сообщение об ошибке отображается без второго предложения.  
  
 Данная ошибка показана в следующем коде.  
  
```vb#  
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
  
### Чтобы исправить эту ошибку  
  
-   Попробуйте указать тип данных для параметра или параметров типа, вместо того чтобы полагаться на определение типа.  
  
## См. также  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Универсальные процедуры в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)