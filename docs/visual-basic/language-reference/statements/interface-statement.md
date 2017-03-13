---
title: "Оператор Interface (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Interface"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interface - оператор [Visual Basic]"
  - "интерфейсы, определение интерфейса"
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Оператор Interface (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объявляет имя интерфейса и представляет определения членов, которые входят в интерфейс.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`attributelist`|Необязательный.  См. [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный.  Может принимать следующие значения:<br /><br /> -   [Открытый](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищенный](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный.  См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Обязательный.  Имя этого интерфейса.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный.  Определяет, что это универсальный интерфейс.|  
|`typelist`|Является обязательным, если используется ключевое слово [Of](../../../visual-basic/language-reference/statements/of-clause.md).  Список типов параметров для данного интерфейса.  При желании каждый параметр типа можно объявить как вариант с помощью универсальных модификаторов `In` и `Out`.  См. раздел [Список типов](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный.  Указывает, что этот интерфейс наследует атрибуты и члены другого интерфейса или интерфейсов.  Дополнительные сведения см. в разделе [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Является обязательным, если используется оператор `Inherits`.  Имена интерфейсов, из которых выводится данный интерфейс.|  
|`modifiers`|Необязательный.  Соответствующие модификаторы для определяемого члена интерфейса.|  
|`Property`|Необязательный.  Определяет свойство, которое является членом интерфейса.|  
|`Function`|Необязательный.  Определяет процедуру `Function`, которая является членом интерфейса.|  
|`Sub`|Необязательный.  Определяет процедуру `Sub`, которая является членом интерфейса.|  
|`Event`|Необязательный.  Определяет событие, которое является членом интерфейса.|  
|`Interface`|Необязательный.  Определяет интерфейс, вложенный в данный интерфейс.  Определение вложенного интерфейса должен завершать оператор `End Interface`.|  
|`Class`|Необязательный.  Определяет класс, который является членом интерфейса.  Определение члена класса должен завершать оператор `End Class`.|  
|`Structure`|Необязательный.  Определяет структуру, которая является членом интерфейса.  Определение члена структуры должен завершать оператор `End Structure`.|  
|`membername`|Требуется для каждого свойства, процедуры, события, интерфейса, класса или структуры, определенных как члена интерфейса.  Имя члена.|  
|`End Interface`|Завершает определение `Interface`.|  
  
## Заметки  
 *Интерфейс* определяет набор членов, таких как свойства и процедуры, которые могут реализовать классы и структуры.  Интерфейс определяет только сигнатуры членов, а не их внутреннюю работоспособность.  
  
 Класс или структура реализуют интерфейс, обеспечивая код для каждого члена, определенного в интерфейсе.  Наконец, когда приложение создает экземпляр этого класса или структуры, объект существует и выполняется в памяти.  Дополнительные сведения см. в разделах [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) и [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Объект `Interface` можно использовать только на уровне пространства имен или модуля.  Это означает, что *контекст объявления* для интерфейса должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом, и не может быть процедурой или блоком.  Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Интерфейсы доступа по умолчанию [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Уровни доступа можно настроить с помощью модификаторов доступа.  Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Правила  
  
-   **Вложенные интерфейсы.** Можно определить один интерфейс внутри другого.  Внешний интерфейс вызывается *вмещающим интерфейсом*, а внутренний интерфейс вызывается *вложенным интерфейсом*.  
  
-   **Объявление члена.**  При объявлении атрибута или процедуры указывается в качестве члена интерфейса, при определении указывается только *сигнатура* свойства или процедуры.  Это включает тип элемента \(свойство или процедура\), его параметры и типы параметров, его возвращаемый тип.  Таким образом, определение члена использует только одну строку кода, и операторы завершения, такие как `End Function` или `End Property`, в интерфейсе не допускаются.  
  
     Напротив, при определении перечисления или структуры, вложенного класса или интерфейса, необходимо включить их члены данных.  
  
-   **Модификаторы членов.** Нельзя использовать любые модификаторы доступа при определении модуля членов, а также можно указать [Shared](../../../visual-basic/language-reference/modifiers/shared.md) или любую процедуру модификаторов, за исключением [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).  Можно объявить любой член с [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md), и можно использовать [Default](../../../visual-basic/language-reference/modifiers/default.md) при определении свойства, а также [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) или [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Наследование.** Если интерфейс использует [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), можно указать один или несколько базовых интерфейсов.  Можно наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем.  В таком случае код реализации должен использовать уточнение имени, чтобы указать, какие члены реализуются.  
  
     Интерфейс не может наследовать от другого интерфейса с более строгим уровнем доступа.  Например, интерфейс `Public` не может наследовать от интерфейса `Friend`.  
  
     Интерфейс не может наследовать от интерфейса, вложенного в него.  
  
-   **Реализация.** Когда класс использует оператор [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) для реализации этого интерфейса, он должен реализовать каждый член, объявленный в интерфейсе.  Кроме того, каждая сигнатура в коде реализации должна совпадать с соответствующей сигнатурой, объявленной в этом интерфейсе.  Однако имя члена в коде реализации не может соответствовать имени члена, как объявлено в интерфейсе.  
  
     Когда класс реализует процедуру, он не может определять процедуру как `Shared`.  
  
-   **Атрибут по умолчанию.** В интерфейсе можно объявить не более одного *атрибута по умолчанию*, на который можно ссылаться без использования имени атрибута.  Можно задать такое свойство, объявив его в модификаторе [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
     Обратите внимание, это означает, что в интерфейсе можно определить свойство по умолчанию, только если он ничего не наследует.  
  
## Поведение  
  
-   **Уровень доступа.** Все члены интерфейса неявно имеют уровень доступа [Public](../../../visual-basic/language-reference/modifiers/public.md).  Нельзя использовать модификаторы доступа при определении члена.  Однако класс, реализующий интерфейс, может объявить уровень доступа для каждого реализуемого члена.  
  
     Если присвоить экземпляр класса переменной, уровень доступа к его членам может зависеть от того, является ли тип данных переменной вложенным интерфейсом или реализацией класса.  Это показано в приведенном ниже примере.  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     Если вы получаете доступ к членам класса с помощью `varAsInterface`, все они имеют общий доступ.  Однако если доступ к членам получается с помощью `varAsClass`, процедура `Sub` `doSomething` имеет защищенный доступ.  
  
-   **Область действия.** Область действия интерфейса — его пространство имен, классы, структуры или модули.  
  
     Областью действия для каждого члена интерфейса является весь интерфейс.  
  
-   **Время существования.** Интерфейс сам не имеет времени жизни, так же как и его члены.  Если класс реализует интерфейс и создается объект как экземпляр этого класса, то объект имеет время жизни в приложении, в котором он выполняется.  Дополнительные сведения содержатся в разделе "Время жизни" в [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## Пример  
 В следующем примере используется оператор `Interface`для определения интерфейса с именем `thisInterface`, который должен быть реализован с помощью оператора `Property` и оператора `Function`.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 Обратите внимание, что операторы `Property` и `Function` не вводят блоков, заканчивающихся на `End Property` и `End Function` в интерфейсе.  Интерфейс определяет только сигнатуры своих членов.  Полные блоки `Property` и `Function` появляются в классе, который реализует `thisInterface`.  
  
## См. также  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Вариативность в универсальных интерфейсах](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)