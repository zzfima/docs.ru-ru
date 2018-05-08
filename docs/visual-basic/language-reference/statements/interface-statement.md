---
title: Оператор Interface (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: f4282778db2d95f701cadb8bb98ec8ca982ba663
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|`attributelist`|Необязательный. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Обязательно. Имя этого интерфейса. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный. Указывает, что это универсальный интерфейс.|  
|`typelist`|Является обязательным, если используется [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Список параметров типа для этого интерфейса. Кроме того, каждый параметр типа можно объявить как вариант с использованием `In` и `Out` универсальных модификаторов. В разделе [введите список](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный. Указывает, что этот интерфейс наследует атрибуты и члены другого интерфейса или интерфейсов. В разделе [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Является обязательным, если используется `Inherits` инструкции. Имена интерфейсов, из которых производится данный интерфейс.|  
|`modifiers`|Необязательный. Соответствующие модификаторы для определяемого члена интерфейса.|  
|`Property`|Необязательный. Определяет свойство, которое является членом интерфейса.|  
|`Function`|Необязательный. Определяет `Function` процедуру, которая является членом интерфейса.|  
|`Sub`|Необязательный. Определяет `Sub` процедуру, которая является членом интерфейса.|  
|`Event`|Необязательный. Определяет событие, которое является членом интерфейса.|  
|`Interface`|Необязательный. Определяет интерфейс, вложенный в этот интерфейс. Определение вложенного интерфейса должен завершать `End Interface` инструкции.|  
|`Class`|Необязательный. Определяет класс, который является членом интерфейса. Определение члена класса должен завершать `End Class` инструкции.|  
|`Structure`|Необязательный. Определяет структуру, которая является членом интерфейса. Определение члена структуры должен завершать `End Structure` инструкции.|  
|`membername`|Требуется для каждого свойства, процедуры, события, интерфейса, класса или структуры, определенных как члена интерфейса. Имя элемента.|  
|`End Interface`|Завершает `Interface` определения.|  
  
## <a name="remarks"></a>Примечания  
 *Интерфейс* определяет набор элементов, таких как можно реализовать свойства и процедуры, которые классы и структуры. Интерфейс определяет только сигнатуры членов, а не их внутреннюю работоспособность.  
  
 Класс или структура реализует интерфейс путем предоставления кода для каждого члена, определенного в интерфейсе. Наконец когда приложение создает экземпляр этого класса или структуры, объект существует и выполняется в памяти. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Можно использовать `Interface` только на уровне пространства имен или модуля. Это означает *контекст объявления* для интерфейса должен быть исходным файлом, пространства имен, класса, структуры, модуля или интерфейса и не может быть процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 По умолчанию для интерфейсов [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
-   **Вложенные интерфейсы.** Можно определить один интерфейс внутри другого. Внешний интерфейс вызывается *содержит интерфейс*, и внутренний интерфейс вызывается *вложенного интерфейса*.  
  
-   **Объявление члена.** При объявлении свойства или процедуры, как член интерфейса, вы определяете только *подписи* свойства или процедуры. Это включает тип элемента (свойство или процедура), его параметры и типы параметров и тип возвращаемого им значения. По этой причине определение члена использует только одну строку кода и завершающий таких инструкциях, как `End Function` или `End Property` не допускаются в интерфейсе.  
  
     Напротив при определении перечисления или структуры, вложенного класса или интерфейса, необходимо включить их члены данных.  
  
-   **Модификаторы членов.** Нельзя использовать модификаторы доступа при определении модуля членов, а также задавать [Shared](../../../visual-basic/language-reference/modifiers/shared.md) или любую процедуру модификаторов, за исключением [перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md). Можно объявить любой член с [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md), и можно использовать [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) при определении свойства, а также [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) или [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Наследование.** Если интерфейс использует [инструкцию наследует](../../../visual-basic/language-reference/statements/inherits-statement.md), можно указать один или несколько базовых интерфейсов. Можно наследовать от двух интерфейсов, даже если каждый из них определяют член с тем же именем. При этом код реализации должен использовать уточнение имени, чтобы указать, какие члены, он реализует.  
  
     Интерфейс не может наследовать от другого интерфейса с более строгим уровнем доступа. Например `Public` интерфейс не может наследовать от `Friend` интерфейса.  
  
     Интерфейс не может наследовать от интерфейса, вложенного в него.  
  
-   **Реализация.** Когда класс использует [реализует](../../../visual-basic/language-reference/statements/implements-clause.md) инструкции для реализации этого интерфейса, он должен реализовывать каждый член, объявленный в интерфейсе. Кроме того каждая сигнатура в коде реализации должна совпадать соответствующей сигнатурой, объявленной в этом интерфейсе. Однако имя члена в коде реализации не должно совпадать с именем члена, определенный в интерфейсе.  
  
     Если класс реализует процедуру, он не может определять процедуру как `Shared`.  
  
-   **Свойство по умолчанию.** Интерфейс можно указать только одно свойство в качестве его *свойство по умолчанию*, который можно ссылаться без использования имени свойства. Задать это свойство, объявив ее с [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) модификатор.  
  
     Обратите внимание, что это означает, что интерфейс можно определить свойство по умолчанию только в том случае, если он ничего не наследует.  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** Все члены интерфейса неявно имеют [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа. Нельзя использовать модификаторы доступа при определении элемента. Однако класс, реализующий интерфейс можно объявить уровень доступа для каждого реализуемого члена.  
  
     Если присвоить экземпляр класса переменной, уровень доступа к его членам может зависеть от является ли тип данных переменной базового интерфейса или реализации класса. Это показано в следующем примере.  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     Если доступ к членам класса через `varAsInterface`, все они имеют общий доступ. Тем не менее если доступ к членам через `varAsClass`, `Sub` процедура `doSomething` имеет доступ к закрытому.  
  
-   **Область действия.** Интерфейс — область действия пространства имен, класса, структуры или модуля.  
  
     Область для каждого члена интерфейса является весь интерфейс.  
  
-   **Время существования.** Интерфейс сам не имеет время существования, а также выполнять его члены. Если класс реализует интерфейс и объект создается как экземпляр класса, объект имеет время существования в приложении, в котором он выполняется. Дополнительные сведения см. в разделе «Lifetime» в [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Interface` инструкцию, чтобы определить интерфейс с именем `thisInterface`, который должен быть реализован с `Property` инструкции и `Function` инструкции.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 Обратите внимание, что `Property` и `Function` инструкции не добавляют блоки, заканчивая `End Property` и `End Function` в интерфейсе. Интерфейс определяет только подписи своих членов. Полный `Property` и `Function` отображаются блоки в класс, реализующий `thisInterface`.  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Расхождение в универсальных интерфейсах](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
