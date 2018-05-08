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
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="object-variable-assignment-visual-basic"></a>Присваивание объектных переменных (Visual Basic)
Используйте обычный оператор присваивания для назначения объекта переменной объекта. Можно присвоить выражение объекта или [ничего](../../../../visual-basic/language-reference/nothing.md) ключевое слово, как приведенный ниже пример иллюстрирует.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` означает нет объекта, в настоящее время назначен переменной.  
  
## <a name="initialization"></a>Инициализация  
 При запуске кода, переменные инициализируются объекта `Nothing`. Тех, чьи объявления содержат инициализацию инициализируются значениями, задаваемый при выполнении инструкций объявления.  
  
 Можно включить инициализацию в объявление с помощью [New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово. Приведенные ниже операторы объявления объявляют переменные объекта `testUri` и `ver` и присвоить им определенные объекты. Каждый использует один из перегруженных конструкторов соответствующего класса для инициализации объекта.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>Отключение  
 Задание для переменной объекта `Nothing` разрывает связь переменной с конкретным объектом. Это предотвращает случайное изменение объекта при изменении переменной. Он также позволяет проверить, является ли переменная ссылку на допустимый объект, как показано в следующем примере.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Если объект, на который ссылается переменная находится в другом приложении, этот тест не может определить, имеет ли приложение завершается или просто недействительными объекта.  
  
 Объектной переменной со значением `Nothing` также называется *ссылка null*.  
  
## <a name="current-instance"></a>Текущий экземпляр  
 *Текущего экземпляра* объекта является то, в котором в данный момент выполняется код. Поскольку весь код выполняется внутри процедуры, текущий экземпляр является тот, в которой была вызвана процедура.  
  
 `Me` Ключевое слово выступает в качестве объектной переменной, ссылающейся на текущий экземпляр. Если процедура не является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), он может использовать `Me` ключевое слово для получения указателя на текущий экземпляр. Общие процедуры не может быть связан с определенным экземпляром класса.  
  
 С помощью `Me` особенно полезен для передачи текущего экземпляра процедуре другого модуля. Предположим, например, число XML-документов и хотите добавить стандартный текст ко всем из них. В следующем примере определяется процедура для этого.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Каждый объект XML-документа может затем вызвать процедуру и передать ее текущий экземпляр в качестве аргумента. В следующем примере это показано.  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a>См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Как: объявление объектной переменной и присвоение ей объекта в Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
