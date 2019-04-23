---
title: Практическое руководство. Определить, какой тип, переменная объекта ссылается на (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 6499dfce880cc9ce16e5d77887afc0598692f48e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342873"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Практическое руководство. Определить, какой тип, переменная объекта ссылается на (Visual Basic)
Объектная переменная содержит указатель на данные, которые хранятся в другом месте. Тип данных можно изменить во время выполнения. В любой момент, можно использовать <xref:System.Type.GetTypeCode%2A> метод для определения текущего типа времени выполнения или [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) чтобы определить текущий тип времени выполнения совместим с указанным типом.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Для определения точного типа переменной объекта в данный момент ссылается на  
  
1. В объектной переменной, вызывать метод <xref:System.Object.GetType%2A> метод для извлечения <xref:System.Type?displayProperty=nameWithType> объекта.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. На <xref:System.Type?displayProperty=nameWithType> вызовите общий метод <xref:System.Type.GetTypeCode%2A> извлекаемого <xref:System.TypeCode> значение перечисления для типа объекта.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Вы можете протестировать <xref:System.TypeCode> члена перечисления представляют интерес, такие как значение перечисления `Double`.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Чтобы определить, является ли объект тип переменной совместим с указанным типом  
  
-   Используйте `TypeOf` оператор в сочетании с [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) проверяемый объект с `TypeOf`... `Is` выражение.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     `TypeOf`... `Is` возвращает значение `True` совместим ли объект во время выполнения тип с указанным типом.  
  
     Критерий совместимости зависит от того, является ли указанный тип класса, структуры или интерфейса. Как правило типы совместимы, если объект имеет тот же тип, что, наследует или реализует заданный тип. Дополнительные сведения см. в разделе [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Обратите внимание на то, что указанный тип не может быть переменной или выражением. Оно должно быть имя определенного типа, например класс, структура или интерфейс. Сюда входят встроенные типы, такие как `Integer` и `String`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
