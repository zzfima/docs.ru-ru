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
ms.openlocfilehash: f3b57ae45815fbd91cad17cddbed4d01037eb92f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002089"
---
# <a name="property-procedures-visual-basic"></a>Процедуры свойств (Visual Basic)
Процедура свойства — это серия Visual Basic инструкций, которые управляют пользовательским свойством модуля, класса или структуры. Процедуры свойств также называются свойствами *доступа к свойствам*.  
  
 Visual Basic предоставляет следующие процедуры свойств.  
  
- Процедура `Get` возвращает значение свойства. Он вызывается при доступе к свойству в выражении.  
  
- Процедура `Set` задает для свойства значение, включая ссылку на объект. Он вызывается при присвоении значения свойству.  
  
 Обычно процедуры свойств определяются парами с помощью инструкций `Get` и `Set`, но можно определить только одну процедуру, если свойство доступно только для чтения ([Инструкция Get](../../../../visual-basic/language-reference/statements/get-statement.md)) или только для записи ([инструкция SET](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 При использовании автоматического реализуемого свойства можно опустить процедуру `Get` и `Set`. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](./auto-implemented-properties.md).  
  
 Свойства можно определить в классах, структурах и модулях. По умолчанию свойства имеют значение `Public`. Это означает, что их можно вызывать из любого места в приложении, которое может получить доступ к контейнеру свойства.  
  
 Сравнение свойств и переменных см. [в разделе различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Само свойство определяется блоком кода, заключенным в [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) , и оператором `End Property`. Внутри этого блока каждая процедура свойства отображается как внутренний блок, заключенный в оператор объявления (`Get` или `Set`) и соответствующее объявление `End`.  
  
 Синтаксис объявления свойства и его процедур выглядит следующим образом:  
  
```vb  
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
  
 @No__t-0 может указывать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении, а также о том, доступно ли свойство только для чтения или только для записи. @No__t-0 в процедуре `Get` или `Set` может быть любым уровнем, более узким, чем уровень доступа, заданный для самого свойства. Дополнительные сведения см. в разделе [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Тип данных  
 Тип данных свойства и основной уровень доступа определяются в операторе `Property`, а не в процедурах свойств. Свойство может иметь только один тип данных. Например, нельзя определить свойство для хранения значения `Decimal`, но получить значение `Double`.  
  
### <a name="access-level"></a>Уровень доступа  
 Однако можно определить основной уровень доступа для свойства и дополнительно ограничить уровень доступа в одной из его процедур свойств. Например, можно определить свойство `Public`, а затем определить процедуру `Private Set`. Процедура `Get` остается `Public`. Уровень доступа можно изменить только в одной из процедур свойства, и его можно сделать более узким, чем основной уровень доступа. Дополнительные сведения см. в разделе [Практическое руководство. Объявите свойство со смешанными уровнями доступа @ no__t-0.  
  
## <a name="parameter-declaration"></a>Объявление параметра  
 Каждый параметр объявляется так же, как и для [процедур подразделов](./sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal`.  
  
 Для каждого параметра в списке параметров используется следующий синтаксис:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Если параметр является необязательным, необходимо также указать значение по умолчанию в составе объявления. Для указания значения по умолчанию используется следующий синтаксис:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Значение свойства  
 В процедуре `Get` возвращаемое значение предоставляется вызывающему выражению как значение свойства.  
  
 В процедуре `Set` новое значение свойства передается в параметр инструкции `Set`. При явном объявлении параметра необходимо объявить его с тем же типом данных, что и свойство. Если параметр не объявлен, компилятор использует неявный параметр `Value` для представления нового значения, присваиваемого свойству.  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Процедура свойства вызывается неявно путем создания ссылки на свойство. Имя свойства используется так же, как имя переменной, за исключением того, что необходимо указать значения для всех аргументов, которые не являются необязательными, а список аргументов необходимо заключить в круглые скобки. Если аргументы не указаны, можно дополнительно опустить круглые скобки.  
  
 Синтаксис неявного вызова процедуры `Set` выглядит следующим образом:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Синтаксис неявного вызова процедуры `Get` выглядит следующим образом:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Иллюстрация объявления и вызова  
 Следующее свойство сохраняет полное имя как два составных имени: имя и фамилия. Когда вызывающий код считывает `fullName`, процедура `Get` объединяет два составных имени и возвращает полное имя. Когда вызывающий код присваивает новое полное имя, процедура `Set` попытается разбить ее на два составных имени. Если не удается найти пробел, он сохраняется как первое имя.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 В следующем примере показаны типичные вызовы процедур свойств `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Процедуры функций](./function-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создание свойства @ no__t-0
- [Практическое руководство. Вызов процедуры свойства @ no__t-0
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic @ no__t-0
- [Практическое руководство. Помещение значения в свойство @ no__t-0
- [Практическое руководство. Получение значения из свойства @ no__t-0
