---
title: "Оператор Sub (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Sub"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Зарезервированное слово Public, операторы Sub"
  - "процедуры, создание"
  - "объявление процедур, оператор Sub"
  - "аргументы [Visual Basic] Sub-процедуры"
  - "As-ключевое слово, Sub-операторы"
  - "Необязательное ключевое слово Sub-операторы"
  - "объявления, процедуры"
  - "Sub - ключевое слово"
  - "Зарезервированное слово Handles, Sub-операторы"
  - "Protected Friend - ключевые слова"
  - "Зарезервированное слово ParamArray, Sub-операторы"
  - "Implements-ключевое слово, Sub-операторы"
  - "Sub - оператор"
  - "подпрограммы"
  - "Зарезервированное слово ByRef, операторы Sub"
  - "Sub-процедуры, оператор Sub"
  - "рекурсивные процедуры"
  - "Зарезервированное слово Private, Sub-операторы"
  - "Зарезервированное слово Friend, Sub-операторы"
  - "Оператор Exit, операторы Sub"
  - "процедуры Sub"
  - "Ключевое слово End Sub-операторы"
  - "Зарезервированное слово ByVal, операторы Sub"
  - "Код Visual Basic, Sub-процедуры"
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
caps.handback.revision: 52
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Sub (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявляет имя, параметры и код, определяющие `Sub` процедуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Части  
  
-   `attributelist`  
  
     Необязательный. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Partial`  
  
     Необязательный. Указывает определение разделяемого метода. В разделе [разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     См. раздел [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Необязательный. В разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный. В разделе [тени](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Необязательный. В разделе [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `name`  
  
     Обязательный. Имя процедуры. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово. Дополнительные сведения см. в разделе [время жизни объекта: как объекты, создание и удаление](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Необязательный. Список параметров типа для универсальной процедуры. В разделе [Введите список](../../../visual-basic/language-reference/statements/type-list.md).  
  
-   `parameterlist`  
  
     Необязательный. Список имен локальных переменных, представляющих параметры этой процедуры. В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `Implements`  
  
     Необязательный. Указывает, что эта процедура реализует один или несколько `Sub` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой. В разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Sub`.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.  
  
     `interface.definedname`  
  
    |||  
    |-|-|  
    |Отделение|Описание|  
    |`interface`|Обязательный. Имя интерфейса, реализуемого данной процедурой, содержащей класс или структуру.|  
    |`definedname`|Обязательный. Имя, под которым процедура определена в `interface`.|  
  
-   `Handles`  
  
     Необязательный. Указывает, что эта процедура может обрабатывать одно или несколько конкретных событий. В разделе [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
-   `eventlist`  
  
     Является обязательным, если предоставлен параметр `Handles`. Список событий, которые обрабатывает данная процедура.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.  
  
     `eventvariable.event`  
  
    |||  
    |-|-|  
    |Отделение|Описание|  
    |`eventvariable`|Обязательный. Объектная переменная объявлена с типом данных класса или структуры, который вызывает событие.|  
    |`event`|Обязательный. Имя события, которое обрабатывает данная процедура.|  
  
-   `statements`  
  
     Необязательный. Блок операторов для выполнения этой процедуры.  
  
-   `End Sub`  
  
     Завершает определение данной процедуры.  
  
## <a name="remarks"></a>Примечания  
 Весь исполняемый код должен быть внутри процедуры. Используйте `Sub` процедуру, когда не требуется возвращать значение вызывающему коду. Используйте `Function` процедуры при необходимости возвращать значение.  
  
## <a name="defining-a-sub-procedure"></a>Определение процедуры Sub  
 Можно определить `Sub` процедуры только на уровне модуля. Контекст объявления подпроцедуры поэтому необходимо класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 `Sub` процедуры по умолчанию для общего доступа. Уровни доступа можно настроить с помощью модификаторов доступа.  
  
 Если в процедуре используется `Implements` ключевое слово, содержащего класса или структуры, должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции.  `Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`. Тем не менее имя, по которому определяется интерфейс `Sub` (в `definedname`) не должен совпадать с именем данной процедуры (в `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Возвращение из процедуры Sub  
 Когда `Sub` процедура возвращает вызывающему коду, выполнение продолжается с оператора после оператора, который вызвал его.  
  
 В следующем примере показан возврат из `Sub` процедуры.  
  
```vb#  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
  `Exit Sub` И `Return` инструкции вызывают Немедленный выход из `Sub` процедуры. Любое количество `Exit Sub` и `Return` операторы могут использоваться в любом месте в процедуре, и можно смешивать `Exit Sub` и `Return` инструкции.  
  
## <a name="calling-a-sub-procedure"></a>Вызов процедуры Sub  
 Можно вызвать `Sub` процедуры с помощью имени процедуры в инструкции, следуйте этим именем списка аргументов в скобках. Скобки могут опускаться только в том случае, если не указать никаких аргументов. Тем не менее код является более удобочитаемым, если всегда включать круглые скобки.  
  
 A `Sub` процедуры и `Function` процедуры может содержать параметры и выполнять последовательность операторов. Однако `Function` процедура возвращает значение, а также `Sub` не процедуры. Следовательно, нельзя использовать `Sub` процедуру в выражении.  
  
 Можно использовать `Call` ключевое слово при вызове `Sub` процедура, но это слово не рекомендуется для большинства случаев. Дополнительные сведения см. в разделе [инструкции Call](../../../visual-basic/language-reference/statements/call-statement.md).  
  
 Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности. По этой причине если список аргументов включает выражения, вызывающие другие процедуры не предполагается вызов этих выражений в определенном порядке.  
  
## <a name="async-sub-procedures"></a>Async Sub-процедуры  
 С помощью функции Async можно вызывать асинхронные функции без использования явных обратных вызовов или вручную разделения кода между несколькими функции или лямбда-выражения.  
  
 Если пометить процедуры с [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в процедуре. Если управление достигает `Await` выражения в `Async` процедура, управление возвращается вызывающему объекту и выполняется в процедуре приостанавливается до завершения выполнения ожидаемой задачи. После завершения задачи в процедуре можно возобновить выполнение.  
  
> [!NOTE]
>   `Async` Процедура возвращает вызывающей стороны, при обнаружении либо первый ожидаемый объект, пока не завершена или в конце `Async` достигается процедуру, что произойдет раньше.  
  
 Можно также пометить [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md) с `Async` модификатор.  `Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>. Пример далее в этом разделе показано `Async` функции с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.  
  
 `Async` `Sub` процедуры в основном используются для обработчиков событий, где значение не может быть возвращен.  `Async``Sub` Процедуру нельзя ожидать и код, вызывающий `Async``Sub` процедуры не могут перехватывать исключения, `Sub` вызывает процедуру.  
  
  `Async` Процедура не может объявить все [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.  
  
 Дополнительные сведения о `Async` процедурах см [асинхронное программирование с использованием Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md), [поток управления в асинхронных программах](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md), и [возвращают типы Async](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Sub` инструкции для определения имени, параметров и кода, образующих текст `Sub` процедуры.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `DelayAsync` — `Async``Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>. `DelayAsync` имеет инструкцию `Return`, которая возвращает целое число. Таким образом, объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`. Так как возвращаемый тип является `Task(Of Integer)`, вычисление `Await` выражения в `DoSomethingAsync` возвращает целое число, как показано в следующей инструкции: `Dim result As Integer = Await delayTask`.  
  
  `startButton_Click` Процедура является примером `Async Sub` процедуры. Поскольку `DoSomethingAsync` является `Async` функции, задача для вызова `DoSomethingAsync` должен ожидать, как показано в следующей инструкции: `Await DoSomethingAsync()`.  `startButton_Click``Sub` Процедура должна быть определена с `Async` модификатор из-за `Await` выражение.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Оператор Call](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Из](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Практическое руководство: использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)