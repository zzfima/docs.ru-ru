---
title: "Практическое руководство. Определение типа, на который указывает объектная переменная (Visual Basic) | Microsoft Docs"
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
  - "объектные переменные, определяющий тип"
  - "TypeOf - оператор [Visual Basic], определение типа переменных объекта"
  - "переменные [Visual Basic], объект"
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Определение типа, на который указывает объектная переменная (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объектная переменная содержит указатель на данные, хранящиеся в другом месте.  Тип этих данных можно изменить во время выполнения.  В любой момент времени можно использовать метод <xref:System.Type.GetTypeCode%2A> для определения текущего типа времени выполнения, или [Оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md), чтобы узнать, совместим ли текущий тип времени выполнения с указанным типом.  
  
### Точное определение типа, на который указывает объектная переменная  
  
1.  В объектной переменной вызовите метод <xref:System.Object.GetType%2A> для извлечения объекта <xref:System.Type?displayProperty=fullName>.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  В классе <xref:System.Type?displayProperty=fullName> вызовите общий метод <xref:System.Type.GetTypeCode%2A> для извлечения значения перечисления <xref:System.TypeCode> для типа объекта.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Можно проверить значение перечисления <xref:System.TypeCode> для любого интересующего члена перечисления, например `Double`.  
  
### Определение совместимости типа объектной переменной с указанным типом  
  
-   Используйте оператор `TypeOf` в комбинации с [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) для проверки объекта с помощью выражения `TypeOf`...`Is`.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     Выражение `TypeOf`...`Is` возвращает значение `True`, если тип объекта времени выполнения совместим с указанным типом.  
  
     Критерий совместимости зависит от того, является ли указанный тип классом, структурой или интерфейсом.  В общем случае типы совместимы, если объект имеет тот же тип, который наследуется из заданного типа или используется им.  Дополнительные сведения см. в разделе [Оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## Компиляция кода  
 Обратите внимание, что указанный тип не может быть переменной или выражением.  Он должен быть именем определенного типа, например класса, структуры или интерфейса.  Кроме того, допускаются встроенные типы, например `Integer` и `String`.  
  
## См. также  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.GetTypeCode%2A>   
 <xref:System.TypeCode>   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)