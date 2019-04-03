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
ms.openlocfilehash: dff1b9bb9e87f827663786cac3f33531db41b2c1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840280"
---
# <a name="object-variable-assignment-visual-basic"></a>Присваивание объектных переменных (Visual Basic)
Чтобы назначить объект в переменной объекта использовать обычный оператор присваивания. Можно назначить выражение объекта или [Nothing](../../../../visual-basic/language-reference/nothing.md) ключевое слово, как показано следующем примере.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` означает, что объект отсутствует в данный момент присваивается переменной.  
  
## <a name="initialization"></a>Инициализация  
 При запуске кода, ваш объект переменные инициализируются `Nothing`. Тех, чьи объявления содержат инициализацию повторно инициализируются значениями, которые вы указали при выполнении инструкций объявления.  
  
 Можно включить инициализации в объявлении с помощью [New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово. Приведенные ниже операторы объявления объявляют переменные объекта `testUri` и `ver` и присваивать им определенные объекты. Каждый использует одну из перегруженных конструкторов соответствующего класса для инициализации объекта.  
  
```  
Dim testUri As New System.Uri("https://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>Отключение  
 Задание для переменной объекта `Nothing` разрывает связь переменной с конкретным объектом. Это предотвращает случайное изменение объекта можно изменить переменную. Он также позволяет проверить ли переменная объекта указывает на допустимый объект, как показано в следующем примере.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Если объект, который ссылается переменная находится в другом приложении, этот тест не может определить, имеет ли это приложение завершается или просто недействительным объекта.  
  
 Переменной объекта со значением `Nothing` также называется *ссылка на null*.  
  
## <a name="current-instance"></a>Текущий экземпляр  
 *Текущего экземпляра* объекта является тот, в котором в данный момент выполняется код. Поскольку весь код выполняется внутри процедуры, текущий экземпляр является тот, в которой была вызвана процедура.  
  
 `Me` Ключевое слово выступает в качестве объектной переменной, ссылающейся на текущий экземпляр. Если процедура не является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), он может использовать `Me` ключевое слово для получения указателя на текущий экземпляр. Общие процедуры не может быть связан с определенным экземпляром класса.  
  
 С помощью `Me` особенно полезна для передачи текущего экземпляра в процедуру в другом модуле. Например предположим, имеют ряд XML-документов и хотите добавить стандартный текст к каждому из них. В следующем примере определяется процедура для этого.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Каждый объект документа XML может вызвать процедуру и передайте его текущего экземпляра в качестве аргумента. В следующем примере это показано.  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a>См. также

- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Практическое руководство. Объявление объектной переменной и присвоение объекта в Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Практическое руководство. Сделать переменная объекта ссылается на какой экземпляр](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
