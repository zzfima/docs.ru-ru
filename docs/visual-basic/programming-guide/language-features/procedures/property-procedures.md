---
title: "Процедуры свойств (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "оператор Set, процедуры свойств"
  - "код Visual Basic, процедуры"
  - "возвращаемые значения, процедуры свойств"
  - "синтаксис, процедуры свойств"
  - "процедуры, свойство"
  - "код Visual Basic, свойства"
  - "процедуры, вызов"
  - "свойства [Visual Basic], пользовательские"
  - "процедуры свойств"
  - "оператор Get, процедуры свойств"
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Процедуры свойств (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Процедура свойства — это последовательность операторов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], выполняющих действия над пользовательским свойством в модуле, классе или структуре.  Процедуру свойства также называют *методом доступа к свойству*.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет следующие процедуры свойств.  
  
-   Процедура `Get` возвращает значение свойства.  Она вызывается при доступе к свойству в выражении.  
  
-   Процедура `Set` устанавливает значение свойства, включая ссылку на объект.  Она вызывается при присвоении значения свойству.  
  
 Обычно процедуры свойств определяются парами с помощью операторов `Get` и `Set`, но можно определить и одиночную процедуру, если свойство доступно только для чтения \([Оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)\) или только для записи \([Оператор Set](../../../../visual-basic/language-reference/statements/set-statement.md)\).  
  
 Можно опустить процедуры `Get` и `Set` при использовании автоматически реализуемого свойства.  Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Свойства можно определять в модулях, классах и структурах.  По умолчанию свойства являются `Public`, что означает, что их можно вызывать из любого места в приложении, имеющего доступ к контейнеру свойства.  
  
 Сравнение свойств и переменных содержится в разделе [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## Синтаксис объявления  
 Само свойство определяется с помощью блока кода, заключенного между операторами [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) и `End Property`.  Внутри этого блока каждая процедура свойства отображается в виде внутреннего блока, заключенного в операторе объявления \(`Get` или `Set`\) и соответствующем объявлении `End`.  
  
 Для объявления свойства и его процедур используется следующий синтаксис:  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 `Modifiers` могут указать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении, а также является ли свойство доступным только для чтения или только для записи.  `AccessLevel` на процедуру `Get` или `Set` может быть любого уровня, более строгим, чем уровень доступа, указанный для самого свойства.  Дополнительные сведения см. в разделе [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### Тип данных  
 Тип данных свойства и уровень доступа определяются в операторе `Property`, а не в процедурах свойства.  Свойство может иметь только один тип данных.  Например, невозможно определить свойство для хранения значений `Decimal`, но извлечь значение `Double`.  
  
### Уровень доступа  
 Тем не менее, можно определить основной уровень доступа для свойства и ограничить уровень доступа в одной из его процедур.  Например, можно определить свойство `Public` и затем определить процедуру `Private Set`.  Процедура `Get` остается `Public`.  Можно изменить уровень доступа только в одной из процедур свойств и сделать его более строгим, чем основной уровень доступа.  Дополнительные сведения см. в разделе [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md).  
  
## Объявление параметра  
 Каждый параметр объявляется таким же образом, как и для [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal`.  
  
 Для каждого параметра в списке параметров синтаксис выглядит следующим образом:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Если параметр является необязательным, необходимо также как часть объявления указать его значение по умолчанию.  Синтаксис для указания значения по умолчанию выглядит следующим образом:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## Значение свойства  
 В процедуре `Get` возвращаемое значение передается в вызывающее выражение в качестве значения свойства.  
  
 В процедуре `Set` новое значение свойства передается параметру оператора `Set`.  Если параметр объявляется явным образом, необходимо объявить его с тем же типом данных, что и свойство.  Если параметр не объявлен, компилятор использует неявный параметр `Value` для присвоения нового значения свойству.  
  
## Синтаксис вызова  
 Процедура свойства вызывается неявно путем создания ссылки на свойство.  Имя свойства используется так же, как имя переменной, за исключением того, что должны быть заданы значения для всех обязательных аргументов, а список аргументов должен быть заключен в скобки.  Если не указано никаких аргументов, скобки можно опустить \(необязательно\).  
  
 При неявном вызове процедуры `Set` используется следующий синтаксис:  
  
 `propertyname[(argumentlist)] = expression`  
  
 При неявном вызове процедуры `Get` используется следующий синтаксис:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### Пример объявления и вызова  
 Следующее свойство сохраняет полное имя как два составных имени, то есть имя и фамилию.  Когда вызывающий код считывает `fullName`, процедура `Get` объединяет два составных имени и возвращает полное имя.  Когда вызывающий код присваивает новое полное имя, процедура `Set` пытается разделить его на два составных имени.  Если не удается найти пробел, то она сохраняет все полное имя как имя.  
  
 [!code-vb[VbVbcnProcedures#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 В следующем примере показаны вызовы процедур свойств из `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Практическое руководство. Создание свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Практическое руководство. Вызов процедуры свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство. Запись значения в свойство](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Практическое руководство. Получение значения из свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)