---
title: Оператор Sub (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: 9a806f2ec979699f7ccf4012c6477bee11301b0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
  
     Необязательный. В разделе [общих](../modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный. В разделе [Shadows](../modifiers/shadows.md).  
  
-   `Async`  
  
     Необязательный. В разделе [Async](../modifiers/async.md).  
  
-   `name`  
  
     Обязательно. Имя процедуры. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово. Дополнительные сведения см. в разделе [время существования объекта: как объекты, создание и удаление](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
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
    |`interface`|Обязательно. Имя интерфейса, реализуемого данной процедурой, содержащего класса или структуры.|  
    |`definedname`|Обязательно. Имя, под которым процедура определена в `interface`.|  
  
-   `Handles`  
  
     Необязательный. Указывает, что эта процедура может обрабатывать одно или несколько конкретных событий. В разделе [обрабатывает](handles-clause.md).  
  
-   `eventlist`  
  
     Является обязательным, если предоставлен параметр `Handles`. Список событий, которые обрабатывает данная процедура.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.  
  
     `eventvariable.event`  
  
    |Отделение|Описание|  
    |---|---|  
    |`eventvariable`|Обязательно. Объектная переменная объявлена с типом данных класса или структуры, который инициирует событие.|  
    |`event`|Обязательно. Имя события, которое обрабатывает данная процедура.|  
  
-   `statements`  
  
     Необязательный. Блок операторов для работы в рамках этой процедуры.  
  
-   `End Sub`  
  
     Завершает определение данной процедуры.  
  
## <a name="remarks"></a>Примечания  
 Весь исполняемый код должен быть внутри процедуры. Используйте `Sub` процедуру, когда не требуется возвращать значение вызывающему коду. Используйте `Function` процедуру, когда требуется вернуть значение.  
  
## <a name="defining-a-sub-procedure"></a>Определение процедуры Sub  
 Можно определить `Sub` процедуры только на уровне модуля. Контекст объявления подпроцедуры таким образом, должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедура или блок. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).  
  
 `Sub` процедуры по умолчанию для общего доступа. Уровни доступа можно настроить с помощью модификаторов доступа.  
  
 Если в процедуре используется `Implements` ключевое слово, содержащего класса или структуры, должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`. Тем не менее имя, по которому интерфейс определяет `Sub` (в `definedname`) не должен совпадать с именем этой процедуры (в `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Возвращение из процедуры Sub  
 Когда `Sub` процедура возвращает в вызывающий код, выполнение продолжается с оператора после инструкции, который вызвал его.  
  
 В следующем примере показан возврат из `Sub` процедуры.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 `Exit Sub` И `Return` инструкции вызывают Немедленный выход из `Sub` процедуры. Любое количество `Exit Sub` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Sub` и `Return` инструкции.  
  
## <a name="calling-a-sub-procedure"></a>Вызов процедуры Sub  
 Вызывается `Sub` процедуры с помощью имени процедуры в инструкции и затем согласно этим именем его список аргументов, заключенный в круглые скобки. Круглые скобки можно опустить только в том случае, если никакие аргументы не передаются. Тем не менее код является более удобочитаемым, если всегда использовать круглые скобки.  
  
 Объект `Sub` процедуры и `Function` процедуры могут содержать параметры и выполнять последовательность операторов. Тем не менее `Function` процедура возвращает значение, а также `Sub` не процедуры. Следовательно, нельзя использовать `Sub` процедуры в выражении.  
  
 Можно использовать `Call` ключевое слово, при вызове `Sub` процедура, но его не рекомендуется для большинства случаев. Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).  
  
 Visual Basic иногда упорядочение арифметические выражения для повышения внутренней эффективности. По этой причине если ваш список аргументов включает выражения, вызывающие другие процедуры не следует предполагается, что эти выражения будет вызываться в определенном порядке.  
  
## <a name="async-sub-procedures"></a>Async Sub-процедуры  
 С помощью функции Async можно вызывать асинхронные функции без использованию явных обратных вызовов или ручному разделению кода между несколькими функции или лямбда-выражения.  
  
 Если пометить процедуры с [Async](../modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в процедуре. Когда управление достигает `Await` выражения в `Async` процедуры, управление возвращается вызывающему объекту и выполнение в процедуре приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи можно возобновить выполнение в процедуре.  
  
> [!NOTE]
>  `Async` Процедура возвращает вызывающий объект при обнаружении либо первый ожидаемый объект, пока не завершена или в конце `Async` достигается процедуры, какое событие происходит раньше.  
  
 Можно также пометить [Function, инструкция](function-statement.md) с `Async` модификатор. `Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>. Пример далее в этом разделе показано, `Async` функции, которая имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task%601>.  
  
 `Async` `Sub` процедуры в основном используются для обработчиков событий, в которой не может быть возвращено значение. `Async``Sub` Процедуру нельзя ожидать и код, вызывающий `Async``Sub` процедуры не могут перехватывать исключения, `Sub` процедура вызывает исключение.  
  
 `Async` Процедура не может объявить все [ByRef](../modifiers/byref.md) параметров.  
  
 Дополнительные сведения о `Async` процедуры см. в разделе [асинхронное программирование с использованием ключевых слов Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Sub` инструкции для определения имени, параметров и кода, образующих текст `Sub` процедуры.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `DelayAsync` — `Async``Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>. `DelayAsync` имеет инструкцию `Return`, которая возвращает целое число. Таким образом, объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`. Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражения в `DoSomethingAsync` создает целое число, как показывает следующая инструкция: `Dim result As Integer = Await delayTask`.  
  
 `startButton_Click` Процедура является примером `Async Sub` процедуры. Поскольку `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показывает следующая инструкция: `Await DoSomethingAsync()`. `startButton_Click``Sub` Процедура должна быть определена с `Async` модификатор из-за `Await` выражение.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](implements-statement.md)  
 [Оператор Function](function-statement.md)  
 [Список параметров](parameter-list.md)  
 [Оператор Dim](dim-statement.md)  
 [Оператор Call](call-statement.md)  
 [Of](of-clause.md)  
 [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [Разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
