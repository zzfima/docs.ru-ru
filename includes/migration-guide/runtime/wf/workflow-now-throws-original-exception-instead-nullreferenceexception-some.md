---
ms.openlocfilehash: 6e5e90a4cfb862b3bfd74ac5a3715e97a736f598
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802538"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="faa94-101">Рабочий процесс теперь создает исходное исключение вместо NullReferenceException, которое создавалось в некоторых случаях</span><span class="sxs-lookup"><span data-stu-id="faa94-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

|   |   |
|---|---|
|<span data-ttu-id="faa94-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="faa94-102">Details</span></span>|<span data-ttu-id="faa94-103">В .NET Framework 4.6.2 и более ранних версий в тех случаях, когда метод Execute действия рабочего процесса создает исключение со значением <code>null</code> для свойства <xref:System.Exception.Message>, среда выполнения рабочего процесса System.Activities создает исключение <xref:System.NullReferenceException?displayProperty=name>, маскируя исходное исключение. В версии .NET Framework 4.7 создается ранее маскированное исключение.</span><span class="sxs-lookup"><span data-stu-id="faa94-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=name>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>|
|<span data-ttu-id="faa94-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="faa94-104">Suggestion</span></span>|<span data-ttu-id="faa94-105">Если в вашем коде реализуется обработка исключения <xref:System.NullReferenceException?displayProperty=name>, измените его для перехвата исключений, которые могут создаваться настраиваемыми действиями.</span><span class="sxs-lookup"><span data-stu-id="faa94-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=name>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>|
|<span data-ttu-id="faa94-106">Область</span><span class="sxs-lookup"><span data-stu-id="faa94-106">Scope</span></span>|<span data-ttu-id="faa94-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="faa94-107">Minor</span></span>|
|<span data-ttu-id="faa94-108">Версия</span><span class="sxs-lookup"><span data-stu-id="faa94-108">Version</span></span>|<span data-ttu-id="faa94-109">4.7</span><span class="sxs-lookup"><span data-stu-id="faa94-109">4.7</span></span>|
|<span data-ttu-id="faa94-110">Тип</span><span class="sxs-lookup"><span data-stu-id="faa94-110">Type</span></span>|<span data-ttu-id="faa94-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="faa94-111">Runtime</span></span>|
|<span data-ttu-id="faa94-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="faa94-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

