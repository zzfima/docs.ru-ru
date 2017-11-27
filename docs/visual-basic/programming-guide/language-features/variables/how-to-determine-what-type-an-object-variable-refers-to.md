---
title: "Практическое руководство. Определение типа, на который указывает объектная переменная (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5dd6785ecd48be3f0455de63b9e3f13a485ddbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Практическое руководство. Определение типа, на который указывает объектная переменная (Visual Basic)
Объектная переменная содержит указатель на данные, которые хранятся в другом месте. Тип данных можно изменить во время выполнения. В любой момент можно использовать <xref:System.Type.GetTypeCode%2A> метод, чтобы определить текущий тип времени выполнения или [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) принадлежности текущего типа времени выполнения совместим с указанным типом.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Чтобы определить точный тип переменной объекта в данный момент ссылается на  
  
1.  Переменная объекта, вызовите метод <xref:System.Object.GetType%2A> метод для извлечения <xref:System.Type?displayProperty=nameWithType> объекта.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  На <xref:System.Type?displayProperty=nameWithType> вызовите общий метод <xref:System.Type.GetTypeCode%2A> для получения <xref:System.TypeCode> значение перечисления для типа объекта.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Можно проверить <xref:System.TypeCode> значение перечисления для члена перечисления представляют интерес, такие как `Double`.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Чтобы определить, является ли объект тип переменной совместим с указанным типом  
  
-   Используйте `TypeOf` оператор в сочетании с [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) для проверки объекта с `TypeOf`... `Is` выражение.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     `TypeOf`... `Is` возвращает значение `True` совместима ли во время выполнения этого объекта типа с указанным типом.  
  
     Критерий совместимости зависит от того, является ли указанный тип класса, структуры или интерфейса. В общем случае типы совместимы, если объект имеет тот же тип, что, наследует или реализует заданный тип. Дополнительные сведения см. в разделе [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Обратите внимание, что указанный тип не может быть переменной или выражения. Оно должно быть имя определенного типа, например класса, структуры или интерфейса. Это включает встроенные типы, такие как `Integer` и `String`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
