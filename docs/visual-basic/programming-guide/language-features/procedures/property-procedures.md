---
title: "Процедуры свойств (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Set statement, Property procedures
- Visual Basic code, procedures
- return values, Property procedures
- syntax, Property procedures
- procedures, property
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], custom
- property procedures
- Get statement, property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f21d4c7d9bd8f14bbe7284bc08399e7ba6b466c3
ms.lasthandoff: 03/13/2017

---
# <a name="property-procedures-visual-basic"></a>Процедуры свойств (Visual Basic)
Процедура свойства — это последовательность [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] операторы, которые управляют пользовательских свойств для модуля, класса или структуры. Процедуры свойств также называются *свойствам*.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет следующие процедуры свойств.  
  
-   A `Get` процедура возвращает значение свойства. Он вызывается при доступе к свойству в выражении.  
  
-   A `Set` процедуры свойству присваивается значение, включая ссылку на объект. Вызывается, когда значение присваивается свойству.  
  
 Обычно процедуры свойств определяются парами с помощью `Get` и `Set` инструкций, но можно определить и одиночную процедуру, если свойство доступно только для чтения ([оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)) или только для записи ([инструкция Set](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства. Дополнительные сведения см. в разделе [Auto-Implemented свойства](./auto-implemented-properties.md).  
  
 Можно определить свойства в классах, структурах и модули. Свойства, `Public` по умолчанию, что означает их можно вызывать из любого места в приложении, можно получить доступ к контейнеру свойства.  
  
 Сравнение свойств и переменных см. в разделе [различия между свойства и переменные в Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Само свойство определяется с помощью блока кода, заключенного в [оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции. Внутри этого блока каждая процедура свойства отображается в виде внутреннего блока, заключенного в операторе объявления (`Get` или `Set`) и соответствующим `End` объявления.  
  
 Синтаксис объявления свойства и его процедуры выглядит следующим образом:  
  
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
  
 `Modifiers` Можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение, а также является ли свойство только для чтения или только для записи. `AccessLevel` На `Get` или `Set` процедура может быть любого уровня, являющегося более строгим, чем уровень доступа, указанный для самого свойства. Дополнительные сведения см. в разделе [инструкции свойство](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Тип данных  
 Тип данных свойства и уровень доступа определяются в `Property` инструкции, а не в процедурах свойства. Свойство может иметь только один тип данных. Например, невозможно определить свойство для хранения `Decimal` значения, но получить `Double` значение.  
  
### <a name="access-level"></a>Уровень доступа  
 Тем не менее можно определить уровень доступа для свойства и ограничить уровень доступа в одной из его процедур. Например, можно определить `Public` свойства, а затем определите `Private Set` процедуры. `Get` Процедуры остается `Public`. Можно изменить уровень доступа в одной из процедур свойств и можно сделать его более строгим, чем основной уровень доступа. Дополнительные сведения см. в разделе [как: объявление свойства со смешанной уровни доступа](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Объявление параметра  
 Каждый параметр объявляется так же, как для [Sub-процедуры](./sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal`.  
  
 Синтаксис для каждого параметра в списке параметров выглядит следующим образом:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Если аргумент является необязательным, необходимо также указать значение по умолчанию как часть его объявления. Синтаксис для указания значения по умолчанию выглядит следующим образом:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Значение свойства  
 В `Get` процедура, возвращаемое значение передается в вызывающее выражение в качестве значения свойства.  
  
 В `Set` процедура, новое значение свойства передается параметру `Set` инструкции. Если параметр объявлен явным образом, необходимо объявить его с тем же типом данных, как свойство. Если параметр не объявлен, компилятор использует неявный параметр `Value` для представления новое значение, присваиваемое свойству.  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Процедура свойства вызывается неявно путем создания ссылки на свойство. Используется имя свойства так же, как имя переменной, за исключением того, что необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов должен быть заключен в круглые скобки. Если не указано никаких аргументов, скобки можно опустить.  
  
 Синтаксис для неявного вызова функции `Set` используется следующая процедура:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Синтаксис для неявного вызова функции `Get` используется следующая процедура:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующее свойство сохраняет полное имя как два составных имени, имени и фамилии. Когда вызывающий код считывает `fullName`, `Get` процедура объединяет два составных имени и возвращает полное имя. Когда вызывающий код присваивает новое полное имя `Set` процедура пытается разделить его на два составных имени. Если не удается найти пробел, он сохраняет их все как имя.  
  
 [!code-vb[VbVbcnProcedures №&8;](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 В следующем примере показаны вызовы процедур свойств из `fullName`.  
  
 [!code-vb[VbVbcnProcedures №&9;](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Процедуры функций](./function-procedures.md)   
 [Процедуры операторов](./operator-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)   
 [Практическое руководство: создание свойства](./how-to-create-a-property.md)   
 [Практическое руководство: вызов процедуры свойства](./how-to-call-a-property-procedure.md)   
 [Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство: поместить значение в свойстве](./how-to-put-a-value-in-a-property.md)   
 [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
