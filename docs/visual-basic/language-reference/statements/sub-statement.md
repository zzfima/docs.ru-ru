---
title: "Sub Statement (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, Sub statements
- procedures, creating
- declaring procedures, Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword, Sub statements
- Optional keyword, Sub statements
- declarations, procedures
- Sub keyword
- Handles keyword, Sub statements
- Protected Friend keyword
- ParamArray keyword, Sub statements
- Implements keyword, Sub statements
- Sub statement
- subroutines
- ByRef keyword, Sub statements
- Sub procedures, Sub statement
- recursive procedures
- Private keyword, Sub statements
- Friend keyword, Sub statements
- Exit statement, Sub statements
- procedures, Sub
- End keyword, Sub statements
- ByVal keyword, Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0eb78f92f22502d9e8595051361b45d9bf53ed64
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="sub-statement-visual-basic"></a>Оператор Sub (Visual Basic)
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
  
     Необязательный. В разделе [список атрибутов](attribute-list.md).  
  
-   `Partial`  
  
     Необязательный. Указывает определение разделяемого метода. В разделе [разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Public](../modifiers/public.md)  
  
    -   [Protected](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [Закрытые](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Перегрузки](../modifiers/overloads.md)  
  
    -   [Переопределения](../modifiers/overrides.md)  
  
    -   [Переопределяемые](../modifiers/overridable.md)  
  
    -   [NotOverridable](../modifiers/notoverridable.md)  
  
    -   [MustOverride](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Необязательный. В разделе [общего](../modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный. В разделе [тени](../modifiers/shadows.md).  
  
-   `Async`  
  
     Необязательный. В разделе [Async](../modifiers/async.md).  
  
-   `name`  
  
     Обязательный. Имя процедуры. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово. Дополнительные сведения см. в разделе [время жизни объекта: как объекты, создание и удаление](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Необязательный. Список параметров типа для универсальной процедуры. В разделе [введите список](type-list.md).  
  
-   `parameterlist`  
  
     Необязательный. Список имен локальных переменных, представляющих параметры этой процедуры. В разделе [список параметров](parameter-list.md).  
  
-   `Implements`  
  
     Необязательный. Указывает, что эта процедура реализует один или несколько `Sub` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой. В разделе [реализует оператор](implements-statement.md).  
  
-   `implementslist`  
  
     Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Sub`.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.  
  
     `interface.definedname`  
  
    |Отделение|Описание|  
    |---|---|  
    |`interface`|Обязательный. Имя интерфейса, реализуемого данной процедурой, содержащей класс или структуру.|  
    |`definedname`|Обязательный. Имя, под которым процедура определена в `interface`.|  
  
-   `Handles`  
  
     Необязательный. Указывает, что эта процедура может обрабатывать одно или несколько конкретных событий. В разделе [обрабатывает](handles-clause.md).  
  
-   `eventlist`  
  
     Является обязательным, если предоставлен параметр `Handles`. Список событий, которые обрабатывает данная процедура.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.  
  
     `eventvariable.event`  
  
    |Отделение|Описание|  
    |---|---|  
    |`eventvariable`|Обязательный. Объектная переменная объявлена с типом данных класса или структуры, который вызывает событие.|  
    |`event`|Обязательный. Имя события, которое обрабатывает данная процедура.|  
  
-   `statements`  
  
     Необязательный. Блок операторов для выполнения этой процедуры.  
  
-   `End Sub`  
  
     Завершает определение данной процедуры.  
  
## <a name="remarks"></a>Примечания  
 Весь исполняемый код должен быть внутри процедуры. Используйте `Sub` процедуру, когда не требуется возвращать значение вызывающему коду. Используйте `Function` процедуры при необходимости возвращать значение.  
  
## <a name="defining-a-sub-procedure"></a>Определение процедуры Sub  
 Можно определить `Sub` процедуры только на уровне модуля. Контекст объявления подпроцедуры поэтому необходимо класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).  
  
 `Sub`процедуры по умолчанию для общего доступа. Уровни доступа можно настроить с помощью модификаторов доступа.  
  
 Если в процедуре используется `Implements` ключевое слово, содержащего класса или структуры, должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`. Тем не менее имя, по которому определяется интерфейс `Sub` (в `definedname`) не должен совпадать с именем данной процедуры (в `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Возвращение из процедуры Sub  
 Когда `Sub` процедура возвращает вызывающему коду, выполнение продолжается с оператора после оператора, который вызвал его.  
  
 В следующем примере показан возврат из `Sub` процедуры.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 `Exit Sub` И `Return` инструкции вызывают Немедленный выход из `Sub` процедуры. Любое число `Exit Sub` и `Return` операторы могут использоваться в любом месте в процедуре, и можно смешивать `Exit Sub` и `Return` инструкции.  
  
## <a name="calling-a-sub-procedure"></a>Вызов процедуры Sub  
 Можно вызвать `Sub` процедуры с помощью имени процедуры в инструкции, следуйте этим именем списка аргументов в скобках. Скобки могут опускаться только в том случае, если не указать никаких аргументов. Тем не менее код является более удобочитаемым, если всегда включать круглые скобки.  
  
 Объект `Sub` процедуры и `Function` процедуры может содержать параметры и выполнять последовательность операторов. Тем не менее `Function` процедура возвращает значение, а также `Sub` не процедуры. Следовательно, нельзя использовать `Sub` процедуру в выражении.  
  
 Можно использовать `Call` ключевое слово при вызове `Sub` процедура, но это слово не рекомендуется для большинства случаев. Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).  
  
 Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности. По этой причине если список аргументов включает выражения, вызывающие другие процедуры не предполагается вызов этих выражений в определенном порядке.  
  
## <a name="async-sub-procedures"></a>Async Sub-процедуры  
 С помощью функции Async можно вызывать асинхронные функции без использования явных обратных вызовов или вручную разделения кода между несколькими функции или лямбда-выражения.  
  
 Если пометить процедуры с [Async](../modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в процедуре. Если управление достигает `Await` выражения в `Async` процедура, управление возвращается вызывающему объекту и выполняется в процедуре приостанавливается до завершения выполнения ожидаемой задачи. После завершения задачи в процедуре можно возобновить выполнение.  
  
> [!NOTE]
>  `Async` , Возвращает вызывающей стороны, при обнаружении либо первый ожидаемый объект, пока не завершена или в конце `Async` достигается процедуру, что произойдет раньше.  
  
 Можно также пометить [инструкции Function](function-statement.md) с `Async` модификатор. `Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601>или <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> Пример далее в этом разделе показано `Async` функции с возвращаемым типом <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601>  
  
 `Async``Sub` процедуры в основном используются для обработчиков событий, где значение не может быть возвращен. `Async``Sub` Процедуру нельзя ожидать и код, вызывающий `Async``Sub` процедуры не могут перехватывать исключения, `Sub` вызывает процедуру.  
  
 `Async` Процедура не может объявить все [ByRef](../modifiers/byref.md) параметров.  
  
 Дополнительные сведения о `Async` процедурах см [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [Async возвращают типы](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Sub` инструкции для определения имени, параметров и кода, образующих текст `Sub` процедуры.  
  
 [!code-vb[VbVbalrStatements&#58;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `DelayAsync` — `Async``Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> `DelayAsync` имеет инструкцию `Return`, которая возвращает целое число. Таким образом, объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`. Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражения в `DoSomethingAsync` возвращает целое число, как показано в следующей инструкции: `Dim result As Integer = Await delayTask`.  
  
 `startButton_Click` Процедура является примером `Async Sub` процедуры. Поскольку `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должен ожидать, как показано в следующей инструкции: `Await DoSomethingAsync()`. `startButton_Click``Sub` Процедура должна быть определена с `Async` модификатор из-за `Await` выражение.  
  
 [!code-vb[csAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](implements-statement.md)   
 [Оператор Function](function-statement.md)   
 [Список параметров](parameter-list.md)   
 [Оператор Dim](dim-statement.md)   
 [Оператор Call](call-statement.md)   
 [Предложение Of (Visual Basic)](of-clause.md)   
 [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Практическое руководство: использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)

