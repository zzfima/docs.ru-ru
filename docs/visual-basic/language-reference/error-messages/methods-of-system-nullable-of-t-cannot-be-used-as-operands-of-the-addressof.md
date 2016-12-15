---
title: "Методы System.Nullable(Of T) нельзя использовать в качестве операндов оператора AddressOf | Microsoft Docs"
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
  - "vbc32126"
  - "bc32126"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32126"
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Методы System.Nullable(Of T) нельзя использовать в качестве операндов оператора AddressOf
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор использует `AddressOf` с операндом, представляющим процедуру структуры <xref:System.Nullable%601>.  
  
 **Идентификатор ошибки**: BC32126  
  
### Чтобы исправить эту ошибку  
  
-   Замените имя процедуры в предложении `AddressOf` на операнд, который не является членом <xref:System.Nullable%601>.  
  
-   Напишите класс\-оболочку для метода <xref:System.Nullable%601>, который необходимо использовать.  В следующем примере определяется класс `NullableWrapper`, определяющий метод `GetValueOrDefault`.  Поскольку этот новый метод не является членом <xref:System.Nullable%601>, он может быть применен к экземпляру типа nullable `nullInstance` для формирования аргумента для `AddressOf`.  
  
    ```vb#  
    Module Module1  
  
        Delegate Function Deleg() As Integer  
  
        Sub Main()  
            Dim nullInstance As New Nullable(Of Integer)(1)  
  
            Dim del As Deleg  
  
            ' GetValueOrDefault is a method of the Nullable generic  
            ' type. It cannot be used as an operand of AddressOf.  
            ' del = AddressOf nullInstance.GetValueOrDefault  
  
            ' The following line uses the GetValueOrDefault method  
            ' defined in the NullableWrapper class.  
            del = AddressOf (New NullableWrapper(  
                Of Integer)(nullInstance)).GetValueOrDefault  
  
            Console.WriteLine(del.Invoke())  
        End Sub  
  
        Class NullableWrapper(Of T As Structure)  
            Private m_Value As Nullable(Of T)  
  
            Sub New(ByVal Value As Nullable(Of T))  
                m_Value = Value  
            End Sub  
  
            Public Function GetValueOrDefault() As T  
                Return m_Value.Value  
            End Function  
        End Class  
    End Module  
    ```  
  
## См. также  
 <xref:System.Nullable%601>   
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Типы значения, допускающие Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)