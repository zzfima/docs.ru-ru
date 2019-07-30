---
title: Присваивание объектных переменных (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 59dea45511ba8d7d10c95cf17e47981124c532e4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631053"
---
# <a name="object-variable-assignment-visual-basic"></a>Присваивание объектных переменных (Visual Basic)

Для назначения объекта объектной переменной используется обычная инструкция присваивания. Можно назначить выражение объекта или ключевое слово [Nothing](../../../../visual-basic/language-reference/nothing.md) , как показано в следующем примере.

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

`Nothing`означает, что для переменной в настоящий момент не назначен объект.

## <a name="initialization"></a>Инициализация

Когда код начинает выполняться, переменные объекта инициализируются значением `Nothing`. Для тех, чьи объявления включают инициализацию, повторно инициализируются значениями, заданными при выполнении инструкций объявления.

Вы можете включить инициализацию в объявление с помощью ключевого слова [New](../../../../visual-basic/language-reference/operators/new-operator.md) . Следующие операторы объявления объявляют переменные `testUri` объекта и `ver` присваивают им определенные объекты. Каждый из них использует один из перегруженных конструкторов соответствующего класса для инициализации объекта.

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a>Рассопоставления

Задание переменной объекта для `Nothing` прекращения сопоставления переменной с каким бы то ни было конкретным объектом. Это предотвращает случайное изменение объекта путем изменения переменной. Он также позволяет проверить, указывает ли объектная переменная на допустимый объект, как показано в следующем примере.

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

Если объект, на который ссылается переменная, находится в другом приложении, этот тест не может определить, было ли приложение завершено, или просто сделает объект недействительным.

Объектная переменная со значением `Nothing` также называется *пустой ссылкой*.

## <a name="current-instance"></a>Текущий экземпляр

*Текущим экземпляром* объекта является тот, в котором выполняется код в данный момент. Поскольку весь код выполняется внутри процедуры, текущим экземпляром является тот, в котором была вызвана процедура.

`Me` Ключевое слово выступает в качестве объектной переменной, ссылающейся на текущий экземпляр. Если процедура не является [общей](../../../../visual-basic/language-reference/modifiers/shared.md), она может использовать `Me` ключевое слово для получения указателя на текущий экземпляр. Общие процедуры не могут быть связаны с конкретным экземпляром класса.

Использование `Me` особенно полезно для передачи текущего экземпляра в процедуру в другом модуле. Например, предположим, что имеется несколько XML-документов и вы хотите добавить к ним некоторый стандартный текст. В следующем примере определяется процедура для этого.

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

Каждый объект XML-документа может затем вызвать процедуру и передать его текущий экземпляр в качестве аргумента. В следующем примере это показано.

```vb
addStandardText(Me)
```

## <a name="see-also"></a>См. также

- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Практическое руководство. Объявите объектную переменную и присвойте ей объект в Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Практическое руководство. Сделать объектную переменную нессылающейся на любой экземпляр](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
