---
ms.openlocfilehash: 4529d8040fc08b5290ac46abd1ef752086ea3aeb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234830"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>Новые (неоднозначные) перегрузки Dispatcher.Invoke могут привести к изменению поведения

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 добавлены новые перегрузки в метод <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType>, включающие параметр типа <xref:System.Action>. Если существующий код перекомпилируется, компиляторы могут разрешить вызовы методов Dispatcher.Invoke, имеющие параметр <xref:System.Delegate>, как вызовы методов Dispatcher.Invoke с параметром <xref:System.Action>. Если вызов перегрузки Dispatcher.Invoke с параметром <xref:System.Delegate> разрешается как вызов перегрузки Dispatcher.Invoke с параметром <xref:System.Action>, возможны следующие различия в поведении.<ul><li>При возникновении исключения события <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> и <xref:System.Windows.Threading.Dispatcher.UnhandledException> не вызываются. Вместо этого исключения обрабатываются событием <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=name>.</li><li>Вызовы некоторых членов, например свойства <xref:System.Windows.Threading.DispatcherOperation.Result>, блокируются до тех пор, пока операция не будет завершена.</li></ul>|
|Предложение|Чтобы избежать неоднозначности (и потенциальных различий в обработке исключений и поведениях блокировки), код, вызывающий Dispatcher.Invoke, может передать пустой object[] как второй параметр в вызов Invoke, чтобы гарантировать разрешение перегрузки метода в .NET Framework 4.0.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li></ul>|
