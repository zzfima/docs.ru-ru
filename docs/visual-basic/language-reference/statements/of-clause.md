---
title: "Предложение Of (Visual Basic) | Microsoft Docs"
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
  - "Of"
  - "vb.Of"
  - "vb.of"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "аргументы [Visual Basic], типы данных"
  - "ограничения, универсальные типы в Visual Basic"
  - "аргументы типа данных"
  - "универсальные параметры"
  - "универсальные шаблоны [Visual Basic], ограничения"
  - "Of - ключевое слово"
  - "параметры, универсальный"
  - "параметры, тип"
  - "параметры типа"
  - "типы [Visual Basic], универсальный"
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Of (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Представляет предложение `Of`, определяющее *параметр типа* в *универсальном* классе, структуре, интерфейсе, делегате или процедуре.  Дополнительные сведения об универсальных типах см. в разделе [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## Использование ключевого слова Of  
 В приведенном ниже примере кода ключевое слово `Of` используется, чтобы определить структуру класса, который имеет два параметра типа.  Оно *ограничивает* параметр `keyType` интерфейсом <xref:System.IComparable>, то есть в коде необходимо указать аргумент\-тип, который реализует параметр <xref:System.IComparable>.  Это необходимо, чтобы процедура `add` могла вызвать метод <xref:System.IComparable.CompareTo%2A?displayProperty=fullName>.  Дополнительные сведения об ограничениях см. в разделе [Список типов](../../../visual-basic/language-reference/statements/type-list.md).  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 Если выполняется предшествующее определение класса, можно создать из него различные классы `dictionary`.  Типы, введенные `entryType` и `keyType`, определяют тип записи в классе и тип ключа, связываемого с каждой записью.  Из\-за ограничений необходимо указать для `keyType` тип, реализующий <xref:System.IComparable>.  
  
 В следующем примере кода создается объект, который содержит записи `String` и связывает ключ `Integer` с каждой из них.  `Integer` реализует <xref:System.IComparable> и таким образом удовлетворяет ограничению на `keyType`.  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 Ключевое слово `Of` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 <xref:System.IComparable>   
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)