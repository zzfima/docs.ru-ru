---
title: Оператор Interface
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: b606f24cf3baa13746834dfbf7ca6b9215fd3558
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348058"
---
# <a name="interface-statement-visual-basic"></a>Оператор Interface (Visual Basic)
Объявляет имя интерфейса и вводит определения членов, содержащихся в интерфейсе.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный элемент. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный элемент. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />[защищенный](../../../visual-basic/language-reference/modifiers/protected.md) -   <br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [защищенный дружественный](../../language-reference/modifiers/protected-friend.md)<br/>- [частный защищенный](../../language-reference/modifiers/private-protected.md)<br /><br /> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный элемент. См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Обязательно. Имя этого интерфейса. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный элемент. Указывает, что это универсальный интерфейс.|  
|`typelist`|Требуется, если используется ключевое слово [of](../../../visual-basic/language-reference/statements/of-clause.md) . Список параметров типа для этого интерфейса. При необходимости каждый параметр типа можно объявить как Variant с помощью `In` и `Out` универсальных модификаторов. См. [список типов](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный элемент. Указывает, что этот интерфейс наследует атрибуты и члены другого интерфейса или интерфейсов. См. раздел [оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Требуется, если используется оператор `Inherits`. Имена интерфейсов, из которых наследуется этот интерфейс.|  
|`modifiers`|Необязательный элемент. Соответствующие модификаторы для определяемого члена интерфейса.|  
|`Property`|Необязательный элемент. Определяет свойство, которое является членом интерфейса.|  
|`Function`|Необязательный элемент. Определяет `Function` процедуру, которая является членом интерфейса.|  
|`Sub`|Необязательный элемент. Определяет `Sub` процедуру, которая является членом интерфейса.|  
|`Event`|Необязательный элемент. Определяет событие, которое является членом интерфейса.|  
|`Interface`|Необязательный элемент. Определяет интерфейс, который является вложенным в этот интерфейс. Определение вложенного интерфейса должно завершаться оператором `End Interface`.|  
|`Class`|Необязательный элемент. Определяет класс, который является членом интерфейса. Определение класса члена должно завершаться оператором `End Class`.|  
|`Structure`|Необязательный элемент. Определяет структуру, которая является членом интерфейса. Определение структуры элемента должно завершаться оператором `End Structure`.|  
|`membername`|Требуется для каждого свойства, процедуры, события, интерфейса, класса или структуры, определенной как член интерфейса. Имя элемента.|  
|`End Interface`|Завершает определение `Interface`.|  
  
## <a name="remarks"></a>Примечания  
 *Интерфейс* определяет набор элементов, таких как свойства и процедуры, которые могут реализовывать классы и структуры. Интерфейс определяет только подписи членов, а не их внутреннюю работу.  
  
 Класс или структура реализует интерфейс путем предоставления кода для каждого члена, определенного интерфейсом. Наконец, когда приложение создает экземпляр из этого класса или структуры, объект существует и выполняется в памяти. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` можно использовать только на уровне пространства имен или модуля. Это означает, что *контекст объявления* для интерфейса должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом и не может быть процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Интерфейсы по умолчанию имеют доступ [Friend](../../../visual-basic/language-reference/modifiers/friend.md) . Уровни доступа можно изменить с помощью модификаторов доступа. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
- **Вложенные интерфейсы.** Можно определить один интерфейс в другом. Внешний интерфейс называется *содержащим интерфейсом*, а внутренний интерфейс называется *вложенным интерфейсом*.  
  
- **Объявление члена.** При объявлении свойства или процедуры в качестве члена интерфейса определяется только *сигнатура* этого свойства или процедуры. Это включает тип элемента (свойство или процедура), его параметры и типы параметров, а также тип возвращаемого значения. В связи с этим определение элемента использует только одну строку кода, а завершающие операторы, такие как `End Function` или `End Property`, недопустимы в интерфейсе.  
  
     Напротив, при определении перечисления или структуры или вложенного класса или интерфейса необходимо включить их члены данных.  
  
- **Модификаторы членов.** Нельзя использовать модификаторы доступа при определении членов модуля, а также нельзя указывать [Общие](../../../visual-basic/language-reference/modifiers/shared.md) или модификаторы процедур, кроме [перегрузок](../../../visual-basic/language-reference/modifiers/overloads.md). Можно объявить любой член с [тенями](../../../visual-basic/language-reference/modifiers/shadows.md), и можно использовать [значение по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) при определении свойства, а также [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) или [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
- **Наследование.** Если интерфейс использует [инструкцию Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), можно указать один или несколько базовых интерфейсов. Можно наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем. В этом случае реализующий код должен использовать уточнение имени, чтобы указать, какой член он реализует.  
  
     Интерфейс не может наследовать от другого интерфейса с более узким уровнем доступа. Например, интерфейс `Public` не может наследовать от интерфейса `Friend`.  
  
     Интерфейс не может наследовать от вложенного в него интерфейса.  
  
- **Реализации.** Если класс использует оператор [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) для реализации этого интерфейса, он должен реализовать каждый член, определенный в интерфейсе. Кроме того, каждая сигнатура в коде реализации должна точно соответствовать соответствующей сигнатуре, определенной в этом интерфейсе. Однако имя члена в коде реализации не обязательно соответствует имени члена, как определено в интерфейсе.  
  
     Когда класс реализует процедуру, он не может обозначать процедуру как `Shared`.  
  
- **Свойство по умолчанию.** Интерфейс может указывать не более одного свойства в качестве *свойства по умолчанию*, на которое можно ссылаться без использования имени свойства. Вы указываете такое свойство, объявляя его с помощью модификатора [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) .  
  
     Обратите внимание, что это означает, что интерфейс может определить свойство по умолчанию только в том случае, если оно наследует None.  
  
## <a name="behavior"></a>Поведение  
  
- **Уровень доступа.** Все члены интерфейса неявно имеют [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ. Нельзя использовать модификатор доступа при определении элемента. Однако класс, реализующий интерфейс, может объявить уровень доступа для каждого реализованного члена.  
  
     Если экземпляр класса назначается переменной, уровень доступа его членов может зависеть от того, является ли тип данных переменной базовым интерфейсом или реализующим классом. Это показано в следующем примере.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     При доступе к членам класса с помощью `varAsInterface`все они имеют общий доступ. Однако при доступе к членам с помощью `varAsClass``Sub` процедура `doSomething` имеет закрытый доступ.  
  
- **Которых.** Областью действия интерфейса является пространство имен, класс, структура или модуль.  
  
     Областью действия каждого члена интерфейса является весь интерфейс.  
  
- **Контролиру.** Интерфейс сам по себе не имеет времени существования и не выполняет его члены. Когда класс реализует интерфейс и объект создается как экземпляр этого класса, объект имеет время существования в приложении, в котором оно выполняется. Дополнительные сведения см. в разделе "время существования" в [операторе Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Interface` используется для определения интерфейса с именем `thisInterface`, который должен быть реализован с помощью оператора `Property` и оператора `Function`.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Обратите внимание, что операторы `Property` и `Function` не представляют блоки, которые заканчиваются `End Property` и `End Function` в интерфейсе. Интерфейс определяет только сигнатуры его членов. Все блоки `Property` и `Function` отображаются в классе, который реализует `thisInterface`.  
  
## <a name="see-also"></a>См. также

- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Расхождение в универсальных интерфейсах](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
