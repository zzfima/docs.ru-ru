---
ms.openlocfilehash: 19c613bf48479cb1e52531a4d6594db8ad89b8f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234870"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load не удаляет свойство символа

|   |   |
|---|---|
|Подробные сведения|При выборе целевой версии платформы .NET Framework 4.5 в конструкторе рабочих процессов и загрузке повторно размещаемого рабочего процесса 3.5 с помощью метода <xref:System.Activities.Presentation.WorkflowDesigner.Load> во время сохранения рабочего процесса создается исключение <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name>.|
|Предложение|Эта ошибка возникает только при нацеливании на .NET Framework 4.5 в конструкторе рабочих процессов, поэтому ее можно устранить, установив <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> в 4.0 .NET Framework. Этой проблемы можно избежать, если использовать метод <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> для загрузки рабочего процесса вместо <xref:System.Activities.Presentation.WorkflowDesigner.Load>.|
|Область|Значительно|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|
