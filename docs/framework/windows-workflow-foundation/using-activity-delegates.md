---
title: Использование делегатов действий
ms.date: 03/30/2017
ms.assetid: e33cf876-8979-440b-9b23-4a12d1139960
ms.openlocfilehash: cbcc8f8e498be4f79f8fed5af7cd3557d7c55981
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837575"
---
# <a name="using-activity-delegates"></a>Использование делегатов действий
Делегаты действий позволяют создателям действий предоставлять обратные вызовы с определенными сигнатурами, для которых пользователи действия могут предоставить обработчики, основанные на действиях. Доступны два типа делегатов действия: <xref:System.Activities.ActivityAction%601> используется для определения делегатов действий, которые не возвращают значение, а <xref:System.Activities.ActivityFunc%601> используется для определения делегатов действий, которые возвращают значение.

Делегаты действий удобно использовать в тех случаях, когда дочерние действия должны быть ограничены необходимостью использования определенной сигнатуры. Например, действие <xref:System.Activities.Statements.While> может содержать любой тип дочернего действия без ограничений, но текстом действия <xref:System.Activities.Statements.ForEach%601> является <xref:System.Activities.ActivityAction%601>; дочернее действие, в конце концов выполняемое <xref:System.Activities.Statements.ForEach%601>, должно иметь <xref:System.Activities.InArgument%601> того же типа элементов коллекции, который перечисляет <xref:System.Activities.Statements.ForEach%601>.

## <a name="using-activityaction"></a>Использование ActivityAction

Некоторые действия [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] используют действия операций, такие как действие <xref:System.Activities.Statements.Catch> и действие <xref:System.Activities.Statements.ForEach%601>. В каждом из случаев действие операции представляет каталог, в котором автор рабочего процесса указывает операцию, обеспечивающую желаемое поведение, при составлении рабочего процесса с использованием одной из подобных операций. В следующем примере для отображения текста в окне консоли использовано действие <xref:System.Activities.Statements.ForEach%601>. Текст <xref:System.Activities.Statements.ForEach%601> определяется с использованием <xref:System.Activities.ActivityAction%601>, совпадающим с типом <xref:System.Activities.Statements.ForEach%601>, указанным в виде строки. Действие <xref:System.Activities.Statements.WriteLine>, указанное в свойстве <xref:System.Activities.ActivityDelegate.Handler%2A>, имеет аргумент <xref:System.Activities.Statements.WriteLine.Text%2A>, привязанный к строковым значениям в коллекции, прохождение по которой производится действием <xref:System.Activities.Statements.ForEach%601>.

[!code-csharp[CFX_ActivityExample#6](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#6)]

Аргумент actionArgument используется для передачи отдельных элементов в коллекции на WriteLine. При вызове рабочего процесса на консоль выводятся следующие данные.

```console
HelloWorld.
```

В примерах в этом разделе используется синтаксис инициализации объектов. Синтаксис инициализации объектов можно использовать для создания определений рабочих процессов в коде, поскольку он обеспечивает иерархическое представление действий в рабочем процессе и показывает связи между действиями. При программном создании рабочих процессов нет необходимости использовать синтаксис инициализации объектов. Следующий пример функционально эквивалентен предыдущему примеру.

[!code-csharp[CFX_ActivityExample#7](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#7)]

Дополнительные сведения об инициализаторах объектов см. [в разделе как инициализировать объекты без вызова конструктораC# (руководство по программированию)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) и [как объявить объект с помощью инициализатора объекта (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).

В следующем примере действие <xref:System.Activities.Statements.TryCatch> используется в рабочем процессе. <xref:System.ApplicationException> вызывается рабочим процессом и обрабатывается действием <xref:System.Activities.Statements.Catch%601>. Обработчик действия <xref:System.Activities.Statements.Catch%601> действия — это <xref:System.Activities.Statements.WriteLine> действие, и сведения об исключении передаются в него с помощью `ex` <xref:System.Activities.DelegateInArgument%601>.

[!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]

При создании пользовательского действия, которое определяет действие <xref:System.Activities.ActivityAction%601>, используйте <xref:System.Activities.Statements.InvokeAction%601> для моделирования вызова этого действия <xref:System.Activities.ActivityAction%601>. В этом примере определяется пользовательское действие `WriteLineWithNotification`. Это действие состоит из объекта <xref:System.Activities.Statements.Sequence>, который содержит действие <xref:System.Activities.Statements.WriteLine>, сопровождаемое действием <xref:System.Activities.Statements.InvokeAction%601>, которое вызывает действие <xref:System.Activities.ActivityAction%601>, принимающее один строковый аргумент.

[!code-csharp[CFX_ActivityExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#1)]

Когда создается рабочий процесс с помощью действия `WriteLineWithNotification`, создатель процесса задает нужную пользовательскую логику в свойстве <xref:System.Activities.ActivityDelegate.Handler%2A> операции действия. В этом примере создается рабочий процесс, использующий действие `WriteLineWithNotification`, а действие <xref:System.Activities.Statements.WriteLine> используется как <xref:System.Activities.ActivityDelegate.Handler%2A>.

[!code-csharp[CFX_ActivityExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#2)]

Существует несколько универсальных версий <xref:System.Activities.Statements.InvokeAction%601> и <xref:System.Activities.ActivityAction%601> для передачи одного или нескольких аргументов.

## <a name="using-activityfunc"></a>Использование ActivityFunc

<xref:System.Activities.ActivityAction%601> используется в случае, когда действие не возвращает результирующего значения, а <xref:System.Activities.ActivityFunc%601> используется, когда результирующее значение возвращается. При создании пользовательского действия, которое определяет действие <xref:System.Activities.ActivityFunc%601>, используйте <xref:System.Activities.Expressions.InvokeFunc%601> для моделирования вызова этого действия <xref:System.Activities.ActivityFunc%601>. В следующем примере определяется действие `WriteFillerText` . Для ввода текста наполнения задается действие <xref:System.Activities.Expressions.InvokeFunc%601>, которое принимает целочисленный аргумент и имеет строковый результат. После извлечения текст наполнения выводится на экран консоли с помощью действия <xref:System.Activities.Statements.WriteLine>.

[!code-csharp[CFX_ActivityExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#3)]

Для ввода текста необходимо использовать действие, которое принимает аргумент `int` и имеет строковый результат. В этом примере показано действие `TextGenerator`, удовлетворяющее этим требованиям.

[!code-csharp[CFX_ActivityExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#4)]

Чтобы использовать действие `TextGenerator` с действием `WriteFillerText`, задайте его в виде <xref:System.Activities.ActivityDelegate.Handler%2A>.

[!code-csharp[CFX_ActivityExample#5](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#5)]
