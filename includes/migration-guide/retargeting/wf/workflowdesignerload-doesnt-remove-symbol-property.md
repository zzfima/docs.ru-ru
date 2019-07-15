---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804646"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="4f8f9-101">WorkflowDesigner.Load не удаляет свойство символа</span><span class="sxs-lookup"><span data-stu-id="4f8f9-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4f8f9-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4f8f9-102">Details</span></span>|<span data-ttu-id="4f8f9-103">При выборе целевой версии платформы .NET Framework 4.5 в конструкторе рабочих процессов и загрузке повторно размещаемого рабочего процесса 3.5 с помощью метода <xref:System.Activities.Presentation.WorkflowDesigner.Load> во время сохранения рабочего процесса создается исключение <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="4f8f9-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> is thrown while saving the workflow.</span></span>|
|<span data-ttu-id="4f8f9-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="4f8f9-104">Suggestion</span></span>|<span data-ttu-id="4f8f9-105">Эта ошибка возникает только при нацеливании на .NET Framework 4.5 в конструкторе рабочих процессов, поэтому ее можно устранить, установив <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> в 4.0 .NET Framework. Этой проблемы можно избежать, если использовать метод <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> для загрузки рабочего процесса вместо <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span><span class="sxs-lookup"><span data-stu-id="4f8f9-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>|
|<span data-ttu-id="4f8f9-106">Область</span><span class="sxs-lookup"><span data-stu-id="4f8f9-106">Scope</span></span>|<span data-ttu-id="4f8f9-107">Значительно</span><span class="sxs-lookup"><span data-stu-id="4f8f9-107">Major</span></span>|
|<span data-ttu-id="4f8f9-108">Версия</span><span class="sxs-lookup"><span data-stu-id="4f8f9-108">Version</span></span>|<span data-ttu-id="4f8f9-109">4.5</span><span class="sxs-lookup"><span data-stu-id="4f8f9-109">4.5</span></span>|
|<span data-ttu-id="4f8f9-110">Тип</span><span class="sxs-lookup"><span data-stu-id="4f8f9-110">Type</span></span>|<span data-ttu-id="4f8f9-111">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="4f8f9-111">Retargeting</span></span>|
|<span data-ttu-id="4f8f9-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4f8f9-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

