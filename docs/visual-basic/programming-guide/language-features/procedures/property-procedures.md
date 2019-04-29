---
title: Процедуры свойств (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: 47e93ee17f160ce5cd701fd0a12ec16b3997ce9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791863"
---
# <a name="property-procedures-visual-basic"></a>Процедуры свойств (Visual Basic)
Процедура свойства — это последовательность операторов Visual Basic, которые управляют пользовательским свойством модуля, класса или структуры. Процедуры свойств также называются *доступа к свойствам*.  
  
 Visual Basic предоставляет следующие процедуры свойств:  
  
- Объект `Get` , возвращает значение свойства. Он вызывается при обращении к свойству в выражении.  
  
- Объект `Set` процедура задает свойство в значение, включая ссылку на объект. Он вызывается при попытке присвоить значение свойству.  
  
 Обычно процедуры свойств определяются парами с помощью `Get` и `Set` инструкций, но можно определить одиночную процедуру, если свойство доступно только для чтения ([оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)) или только для записи ([значение Инструкция](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](./auto-implemented-properties.md).  
  
 Можно определить свойства в классах, структурах и модули. Свойства являются `Public` по умолчанию, означающее, их можно вызывать из любого места в приложении, можно получить доступ к контейнеру свойства.  
  
 Сравнение свойств и переменных, см. в разделе [различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Само свойство определяется с помощью блока кода, заключенного в [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции. Внутри этого блока каждая процедура свойства отображается представляет собой внутренний блок, заключенный в оператор объявления (`Get` или `Set`) и соответствующим `End` объявления.  
  
 Синтаксис для объявления свойства и его процедуры выглядит следующим образом:  
  
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
  
 `Modifiers` Можно указать уровень доступа и сведения о перегрузке, переопределении, совместного использования и затенение, а также, является ли свойство только для чтения или только для записи. `AccessLevel` На `Get` или `Set` процедура может быть любой уровень, который является более ограничивающим, чем уровень доступа, указанный для самого свойства. Дополнительные сведения см. в разделе [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Тип данных  
 Тип данных свойства и уровень доступа определяются в `Property` инструкции, а не в процедурах свойства. Свойство может иметь только одного типа данных. Например, невозможно определить свойство для хранения `Decimal` значение, но получают `Double` значение.  
  
### <a name="access-level"></a>Уровень доступа  
 Тем не менее можно определить уровень доступа для свойства и дополнительно ограничить уровень доступа в одной процедуры свойства. Например, можно определить `Public` свойства, а затем определите `Private Set` процедуры. `Get` Процедуры остается `Public`. Можно изменить уровень доступа только в одной из процедур свойства и его можно только сделать более строгим, чем уровень доступа. Дополнительные сведения см. в разделе [Как Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Объявление параметра  
 Каждый параметр объявляется так же, как и для [подпрограммы](./sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal`.  
  
 Синтаксис для каждого параметра в списке параметров выглядит следующим образом:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Если параметр является необязательным, необходимо также указать значение по умолчанию как часть объявления. Синтаксис для указания значения по умолчанию выглядит следующим образом:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Значение свойства  
 В `Get` процедура, возвращаемое значение передается в вызывающее выражение в качестве значения свойства.  
  
 В `Set` процедуры, новое значение свойства передается в параметр `Set` инструкции. Если вы явно объявить параметр, необходимо объявить ее с тем же типом данных, так как свойство. Если параметр не объявлен, компилятор использует неявный параметр `Value` для представления новое значение, присваиваемое свойству.  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Процедура свойства вызывается неявно путем создания ссылки на свойство. Используется имя свойства так же, лучше использовать имя переменной, за исключением того, что необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов необходимо заключить в круглые скобки. Если не указано никаких аргументов, скобки можно опустить.  
  
 Синтаксис неявный вызов `Set` процедура выглядит следующим образом:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Синтаксис неявный вызов `Get` процедура выглядит следующим образом:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующее свойство сохраняет полное имя как два составных имени, имени и фамилии. Когда вызывающий код считывает `fullName`, `Get` процедура объединяет два составных имени и возвращает полное имя. Когда вызывающий код присваивает новое полное имя, `Set` процедура пытается разделить его на два составных имени. Если не удается найти пробел, он хранит все как имя.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 В следующем примере показано вызовы процедур свойств из `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Процедуры функций](./function-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создать свойство](./how-to-create-a-property.md)
- [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)
- [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
