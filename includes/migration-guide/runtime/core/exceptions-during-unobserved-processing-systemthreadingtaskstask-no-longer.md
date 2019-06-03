---
ms.openlocfilehash: b0e6d6f228647148083d3df64e65f817dc3455d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379585"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>Исключения во время обработки без наблюдения в классе System.Threading.Tasks.Task больше не распространяются на поток метода завершения

|   |   |
|---|---|
|Подробные сведения|Поскольку класс <xref:System.Threading.Tasks.Task?displayProperty=name> представляет асинхронную операцию, он перехватывает все исключения невысокой серьезности, происходящие во время асинхронной обработки. В .NET Framework 4.5, если исключение не наблюдается и код не ожидает задачу, исключение больше не распространяется на поток метода завершения и не приводит к сбою процесса во время сборки мусора. Это изменение повышает надежность приложений, использующих класс Task для выполнения асинхронной обработки без наблюдения.|
|Предложение|Если приложение зависит от асинхронных исключений без наблюдения, распространяющихся на поток метода завершения, можно восстановить прежнее поведение, предоставив соответствующий обработчик для события <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> или задав значение для [элемента конфигурации среды выполнения](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType></li></ul>|
