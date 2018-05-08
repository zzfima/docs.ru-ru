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
ms.openlocfilehash: a0a73494c3573973d88823a7b5a5a83d2672e7d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="property-procedures-visual-basic"></a>Процедуры свойств (Visual Basic)
Процедура свойства — это последовательность операторов Visual Basic, которые позволяют управлять пользовательским свойством модуля, класса или структуры. Процедуры свойств также называются *свойствам*.  
  
 Visual Basic предоставляет следующие процедуры свойств:  
  
-   Объект `Get` процедура возвращает значение свойства. Он вызывается при доступе к свойству в выражении.  
  
-   Объект `Set` процедуры свойству присваивается значение, включая ссылку на объект. Вызывается, когда значение присваивается свойству.  
  
 Обычно процедуры свойств определяются парами с помощью `Get` и `Set` инструкции, но можно определить одиночную процедуру, если свойство доступно только для чтения ([оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)) или только для записи ([значение Инструкция](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](./auto-implemented-properties.md).  
  
 Можно определить свойства в классах, структурах и модулей. Свойства, `Public` по умолчанию, означающее, их можно вызывать из любого места в приложении, можно получить доступ к контейнеру свойства.  
  
 Сравнение свойств и переменных см. в разделе [различия между свойства и переменные в Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Само свойство определяется с помощью блока кода, заключенного в [оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции. Внутри этого блока каждая процедура свойства отображается представляет собой внутренний блок, заключенный в операторе объявления (`Get` или `Set`) и соответствующим `End` объявления.  
  
 Ниже приведен синтаксис для объявления свойства и его процедуры:  
  
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
  
 `Modifiers` Можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение, а также, является ли свойство только для чтения или только для записи. `AccessLevel` На `Get` или `Set` процедура может быть любой уровень, который является более строгим, чем уровень доступа, указанный для самого свойства. Дополнительные сведения см. в разделе [оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Тип данных  
 Тип данных свойства и уровень доступа определяются в `Property` инструкции, а не в процедурах свойства. Свойство может иметь только одного типа данных. Например, невозможно определить свойство для хранения `Decimal` значение, однако получить `Double` значение.  
  
### <a name="access-level"></a>Уровень доступа  
 Тем не менее можно определить уровень доступа для свойства и ограничить уровень доступа в одной процедуры свойства. Например, можно определить `Public` свойства, а затем определите `Private Set` процедуры. `Get` Остается процедуры `Public`. Можно изменить уровень доступа только в одной из процедур свойств, и его можно только сделать более строгим, чем уровень доступа. Дополнительные сведения см. в разделе [как: объявление свойства со смешанной уровни доступа](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Объявление параметра  
 Каждый параметр объявляется так же, как для [Sub-процедуры](./sub-procedures.md), за исключением того, что механизм передачи должен быть `ByVal`.  
  
 Синтаксис для каждого параметра в списке параметров выглядит следующим образом:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Если аргумент является необязательным, необходимо также указать значение по умолчанию как часть объявления. Ниже приведен синтаксис для указания значения по умолчанию:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Значение свойства  
 В `Get` процедуры, возвращаемое значение передается в вызывающее выражение в качестве значения свойства.  
  
 В `Set` процедуры, новое значение свойства передается в параметр `Set` инструкции. Если вы явно объявить параметр, необходимо объявить его с тем же типом данных, как свойство. Если параметр не объявлен, компилятор использует неявный параметр `Value` для представления новое значение, присваиваемое свойству.  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Процедура свойства вызывается неявно путем создания ссылки на свойство. Используется имя свойства так же, как имя переменной, за исключением того, необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргумент должен быть заключен в круглые скобки. Если не указано никаких аргументов, скобки можно опустить.  
  
 Синтаксис неявный вызов `Set` процедура является следующим образом:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Синтаксис неявный вызов `Get` процедура является следующим образом:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующее свойство сохраняет полное имя как два составных имени, имени и фамилии. Когда вызывающий код считывает `fullName`, `Get` процедура объединяет два составных имени и возвращает полное имя. Когда вызывающий код присваивает новое полное имя `Set` процедура пытается разделить его на два составных имени. Если он не находит пробел, он сохраняет все как имя.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 В следующем примере показаны вызовы процедур свойств из `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Процедуры функций](./function-procedures.md)  
 [Процедуры операторов](./operator-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)  
 [Практическое руководство. Создание свойства](./how-to-create-a-property.md)  
 [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)  
 [Как: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)  
 [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
