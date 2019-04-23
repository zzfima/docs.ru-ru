---
ms.openlocfilehash: 94fad6fe910da6c528c5e13f529a6db274e07d5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235922"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Изменение в поведении методов Task.WaitAll с аргументами времени ожидания

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 реализовано согласованное поведение методов <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>. В .NET Framework 4 поведение этих методов было непоследовательным. По истечении времени ожидания, если одна или несколько задач были завершены или отменены до вызова метода, метод вызывал исключение <xref:System.AggregateException?displayProperty=name>. По истечении времени ожидания, если ни одна задача не была завершена или отменена до вызова метода, однако одна или несколько задач входили в эти состояния после вызова метода, метод возвращал значение false.<br/><br/>В .NET Framework 4.5 эти перегрузки метода теперь возвращают false, если все задачи по-прежнему выполняются после истечения времени ожидания, и вызывают исключение <xref:System.AggregateException?displayProperty=name>, только если входная задача была отменена (независимо от того, была ли она до или после вызова метода), а никакие другие задачи не выполняются.|
|Предложение|Если исключение <xref:System.AggregateException?displayProperty=name> было перехвачено с целью обнаружения задачи, которая была отменена до вызова метода <xref:System.Threading.Tasks.Task.WaitAll%2A>, этот код должен выполнить то же обнаружение с помощью свойства <xref:System.Threading.Tasks.Task.IsCanceled%2A> (например, .Any(t =&gt; t.IsCanceled)), так как .NET Framework 4.6 создаст исключение только в том случае, если все ожидаемые задачи завершены до истечения времени ожидания.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|
