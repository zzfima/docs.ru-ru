---
title: Оператор Interface (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: db39759a804905450e7f8913f45e8ddab39d8416
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784193"
---
# <a name="interface-statement-visual-basic"></a>Оператор Interface (Visual Basic)
Объявляет имя интерфейса и представляет определения членов, которые входят в интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|`attributelist`|Необязательный параметр. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный параметр. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Частный защищенный](../../language-reference/modifiers/private-protected.md)<br /><br /> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный параметр. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Обязательный. Имя этого интерфейса. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный параметр. Указывает, что это универсальный интерфейс.|  
|`typelist`|Требуется при использовании [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Список параметров типа для этого интерфейса. При необходимости каждого параметра типа можно объявить как вариант с помощью `In` и `Out` универсального модификаторы. См. в разделе [введите список](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный параметр. Указывает, что этот интерфейс наследует атрибуты и членами другого интерфейса или интерфейсов. См. в разделе [оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Требуется при использовании `Inherits` инструкции. Имена интерфейсов, от которых наследует этот интерфейс.|  
|`modifiers`|Необязательный параметр. Соответствующие модификаторы для определяемого члена интерфейса.|  
|`Property`|Необязательный параметр. Определяет свойство, которое является членом интерфейса.|  
|`Function`|Необязательный параметр. Определяет `Function` процедуру, которая является членом интерфейса.|  
|`Sub`|Необязательный параметр. Определяет `Sub` процедуру, которая является членом интерфейса.|  
|`Event`|Необязательный параметр. Определяет событие, которое является членом интерфейса.|  
|`Interface`|Необязательный параметр. Определяет интерфейс, вложенный в этот интерфейс. Определение вложенного интерфейса должен завершать `End Interface` инструкции.|  
|`Class`|Необязательный параметр. Определяет класс, который является членом интерфейса. Определение члена класса должен завершать `End Class` инструкции.|  
|`Structure`|Необязательный параметр. Определяет структуру, которая является членом интерфейса. Определение члена структуры должен завершать `End Structure` инструкции.|  
|`membername`|Требуется для каждого свойства, процедуры, события, интерфейс, класс или структура, определенная в качестве члена интерфейса. Имя элемента.|  
|`End Interface`|Завершает `Interface` определения.|  
  
## <a name="remarks"></a>Примечания  
 *Интерфейс* определяет набор элементов, таких как можно реализовать свойства и процедуры, которые классы и структуры. Интерфейс определяет только сигнатуры членов, а не их внутреннюю работоспособность.  
  
 Класс или структура реализует интерфейс, указав код для каждого члена, определенные в интерфейсе. Наконец когда приложение создает экземпляр этого класса или структуры, объект существует и выполняется в памяти. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Можно использовать `Interface` только на уровне пространства имен или модуля. Это означает, что *контекст объявления* интерфейс должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс, и не может быть процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Интерфейсы по умолчанию для [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
- **Вложенные интерфейсы.** Можно определить один интерфейс внутри другого. Внешний интерфейс вызывается *содержит интерфейс*, а внутренний интерфейс называется *вложенного интерфейса*.  
  
- **Объявление члена.** При объявлении свойства или процедуры как член интерфейса, определяется только *подпись* свойства или процедуры. Это включает в себя тип элемента (свойство или процедура), его параметры и типы параметров и типом возвращаемого значения. По этой причине определение члена использует только одну строку кода и завершающий операторы, например `End Function` или `End Property` не допускаются в интерфейсе.  
  
     Напротив при определении перечисления или структуры, вложенного класса или интерфейса, бывает необходимо включить их члены данных.  
  
- **Модификаторы члена.** Модификаторы доступа нельзя использовать при определении элементы модуля, а также задавать [Shared](../../../visual-basic/language-reference/modifiers/shared.md) или любую процедуру модификаторов, за исключением [перегружает](../../../visual-basic/language-reference/modifiers/overloads.md). Можно объявить любой член с [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md), и вы можете использовать [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) при определении свойства, а также [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) или [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
- **Наследование.** Если интерфейс использует [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), можно указать один или несколько базовых интерфейсов. Может наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем. Если сделать это, код реализации необходимо использовать уточнение имен, чтобы указать, какие члены, он реализует.  
  
     Интерфейс не может наследовать от другого интерфейса с более строгий уровень доступа. Например `Public` интерфейс не может наследовать от `Friend` интерфейс.  
  
     Интерфейс не может наследовать от вложенного в него интерфейс.  
  
- **Реализация.** Когда класс использует [реализует](../../../visual-basic/language-reference/statements/implements-clause.md) инструкцию, чтобы реализовать этот интерфейс, он должен реализовать каждый член, определенных в этом интерфейсе. Кроме того каждая сигнатура в коде реализации должен точно соответствовать соответствующую подпись, определенными в этом интерфейсе. Однако имя члена в коде реализации не совпадает с именем члена, как определено в интерфейсе.  
  
     Когда класс реализует процедуру, он не может определять в процедуру в качестве `Shared`.  
  
- **Свойство по умолчанию.** Интерфейс можно указать не более одного свойства, как его *свойство по умолчанию*, который можно ссылаться без использования имени свойства. Укажите такое свойство, объявив ее с [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) модификатор.  
  
     Обратите внимание на то, что это означает, что интерфейс можно определить свойство по умолчанию, только в том случае, если он ничего не наследует.  
  
## <a name="behavior"></a>Поведение  
  
- **Уровень доступа.** Все члены интерфейса неявно имеют [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа. Невозможно использовать модификаторы доступа при определении члена. Тем не менее класс, реализующий интерфейс можно объявить уровень доступа для каждой реализации члена.  
  
     Если присвоить экземпляр класса переменной, уровень доступа к членам может основываться на является ли тип данных переменной базового интерфейса или реализующего класса. Это показано в следующем примере.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Если доступ к членам класса через `varAsInterface`, все они имеют общий доступ. Тем не менее если выполняется обращение к членам через `varAsClass`, `Sub` процедуры `doSomething` закрытым.  
  
- **Область.** Область действия его пространства имен, класса, структуры или модуля — интерфейс.  
  
     Область для каждого члена интерфейса является весь интерфейс.  
  
- **Время существования.** Интерфейс сам не имеет время существования, так же как и его члены. Если класс реализует интерфейс и объект создается как экземпляр класса, объект имеет время существования приложения, в котором он выполняется. Дополнительные сведения см. в разделе «Время жизни» в [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Interface` инструкцию, чтобы определить интерфейс с именем `thisInterface`, который должен быть реализован с помощью `Property` инструкции и `Function` инструкции.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Обратите внимание, что `Property` и `Function` инструкций не возникнут новые блоки, заканчивая `End Property` и `End Function` в интерфейсе. Интерфейс определяет только подписи его члены. Полный `Property` и `Function` блоки отображаются в класс, реализующий `thisInterface`.  
  
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
