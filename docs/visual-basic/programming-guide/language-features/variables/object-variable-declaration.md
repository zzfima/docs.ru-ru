---
title: "Объявление переменных объектов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "привязка, раннее и позднее"
  - "классы [Visual Basic], объявление"
  - "объявления, класс"
  - "объявление классов"
  - "объявление переменных, объектные переменные"
  - "раннее связывание"
  - "позднее связывание"
  - "объектные переменные, объявление"
  - "переменные [Visual Basic], объект"
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Объявление переменных объектов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Используйте обычный оператор объявления для объявления объектной переменной.  Для типа данных укажите `Object` \(то есть [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)\) или более определенный класс, из которого будет создан объект.  
  
 Объявление переменной как `Object` аналогично ее объявлению как <xref:System.Object?displayProperty=fullName>.  
  
 При объявлении переменной с указанным объектом класса она получает доступ ко всем методам и свойствам этого класса и классов, от которых он наследуется.  Если объявить переменную с классом <xref:System.Object>, она получает доступ только к членам класса <xref:System.Object>, если не выключить `Option Strict Off`, чтобы разрешить позднее связывание.  
  
## Синтаксис объявления  
 Используйте следующий синтаксис для объявления объектной переменной:  
  
```  
Dim variablename As [New] { objectclass | Object }  
```  
  
 Можно также указать в объявлении [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) или [Static](../../../../visual-basic/language-reference/modifiers/static.md).  Допустимы следующие варианты объявлений:  
  
```  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## Раннее и позднее связывание  
 Иногда определенный класс не известен до выполнения кода.  В этом случае необходимо объявить объектную переменную с типом данных `Object`.  Это создает общую ссылку на любой тип объекта, а определенный класс назначается во время выполнения.  Такой подход называется *поздним связыванием*.  Позднее связывание требует дополнительного времени выполнения.  Такой подход также позволяет использовать в коде только самые последние назначенные ему методы и свойства класса.  Это может вызвать ошибки во время выполнения, если код пытается получить доступ к членам другого класса.  
  
 Если определенный класс известен во время компиляции, следует объявить объектную переменную в этом классе.  Такой подход называется *ранним связыванием*.  Раннее связывание позволяет повысить производительность и гарантирует доступ ко всем методам и свойствам определенного класса.  В предыдущем примере объявлений, если переменная `objA` использует только объекты класса <xref:System.Windows.Forms.Label?displayProperty=fullName>, в ее объявлении следует указать `As System.Windows.Forms.Label`.  
  
### Преимущества раннего связывания  
 Объявление объектной переменной в определенном классе объекта дает следующие преимущества:  
  
-   Автоматическая проверка типа  
  
-   Гарантированный доступ ко всем членам определенного класса  
  
-   Поддержка Microsoft IntelliSense в редакторе кода  
  
-   Улучшение читаемости кода  
  
-   Снижение числа ошибок в коде  
  
-   Обнаружение ошибок во время компиляции, а не во время выполнения  
  
-   Увеличение скорости выполнения кода  
  
## Доступ к членам объектных переменных  
 Если включен `Option Strict` \(`On`\), для объектной переменной доступны методы и свойства только того класса, в котором она объявлена.  Это показано в приведенном ниже примере.  
  
```  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 В этом примере переменная `p` может использовать только члены самого класса <xref:System.Object>, который не включает свойство `Left`.  С другой стороны, `q` была объявлена с типом <xref:System.Windows.Forms.Label> и, следовательно, может использовать все методы и свойства класса <xref:System.Windows.Forms.Label> в пространстве имен <xref:System.Windows.Forms>.  
  
## Гибкость объектных переменных  
 При работе с объектами в иерархии наследования можно выбрать класс, который будет использоваться при объявлении объектных переменных.  Делая этот выбор, необходимо найти баланс между гибкостью присваивания объекта и возможностью доступа к членам класса.  Например, рассмотрим иерархию наследования, которая приводит к классу <xref:System.Windows.Forms.Form?displayProperty=fullName>:  
  
 <xref:System.Object>  
  
 `` <xref:System.ComponentModel.Component>  
  
 `` <xref:System.Windows.Forms.Control>  
  
 `` <xref:System.Windows.Forms.ScrollableControl>  
  
 `` <xref:System.Windows.Forms.ContainerControl>  
  
 `` <xref:System.Windows.Forms.Form>  
  
 Предположим, приложение определяет форму `specialForm`, которая наследуется из класса <xref:System.Windows.Forms.Form>.  Можно объявить объектную переменную, которая специально ссылается на `specialForm`, как показано в следующем примере.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Объявление в предыдущем примере ограничивает переменную `nextForm` до объектов класса `specialForm`, но оно также делает доступными для `specialForm` все методы и свойства класса `nextForm`, а также все члены всех классов из которых наследуется `specialForm`.  
  
 Можно сделать объектную переменную общей, объявив ее переменной типа <xref:System.Windows.Forms.Form>, как показано в следующем примере.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
 Объявление в предыдущем примере позволяет назначить `anyForm` любую форму в приложении.  Однако несмотря на то, что `anyForm` имеет доступ ко всем членам класса <xref:System.Windows.Forms.Form>, она не может использовать дополнительные методы или свойства, определенные для конкретных форм, таких как `specialForm`.  
  
 Все члены базового класса доступны для производных классов, но дополнительные члены производного класса недоступны для базового класса.  
  
## См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [Практическое руководство. Доступ к членам объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)