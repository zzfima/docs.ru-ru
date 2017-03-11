---
title: "Атрибут Extension может быть применен только к объявлениям Module, Sub или Function | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36550"
  - "vbc36550"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36550"
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Единственный способ расширения типа данных в Visual Basic — определение метода расширения внутри стандартного модуля.  Методом расширения могут быть процедуры `Sub` или `Function`.  Все методы расширения должны быть помечены атрибутом расширения `<Extension()>` из пространства имен <xref:System.Runtime.CompilerServices?displayProperty=fullName>.  При необходимости модуль, содержащий метод расширения, может быть помечен таким же образом.  В других случаях использование атрибута расширения невозможно.  
  
 **Идентификатор ошибки:** BC36550  
  
### Чтобы исправить эту ошибку  
  
-   Удалите атрибут расширения.  
  
-   Измените расширение в качестве метода, определенного в заключающем модуле.  
  
## Пример  
 В следующем примере определяется метод `Print` для типа данных `String`.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
  
```  
  
## См. также  
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)