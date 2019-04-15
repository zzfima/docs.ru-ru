---
ms.openlocfilehash: 2278d82d5362fe217ca4bce02a052d4b440843c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236675"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="5a10f-101">ASP.NET MVC теперь экранирует пробелы в строках, переданных через параметры маршрута</span><span class="sxs-lookup"><span data-stu-id="5a10f-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5a10f-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5a10f-102">Details</span></span>|<span data-ttu-id="5a10f-103">Чтобы соответствовать стандарту RFC 2396, пробелы в путях маршрута теперь экранируются при заполнении параметров действий из маршрута.</span><span class="sxs-lookup"><span data-stu-id="5a10f-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="5a10f-104">Таким образом, в то время как <code>/controller/action/some data</code> ранее соответствовал маршруту <code>/controller/action/{data}</code> и предоставлял <code>some data</code> в качестве параметра данных, теперь он будет предоставлять <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="5a10f-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="5a10f-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="5a10f-105">Suggestion</span></span>|<span data-ttu-id="5a10f-106">Код должен быть обновлен для неэкранирования строковых параметров из маршрута.</span><span class="sxs-lookup"><span data-stu-id="5a10f-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="5a10f-107">Если необходим исходный URI, доступ к нему можно получить с помощью API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="5a10f-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="5a10f-108">Область</span><span class="sxs-lookup"><span data-stu-id="5a10f-108">Scope</span></span>|<span data-ttu-id="5a10f-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="5a10f-109">Minor</span></span>|
|<span data-ttu-id="5a10f-110">Версия</span><span class="sxs-lookup"><span data-stu-id="5a10f-110">Version</span></span>|<span data-ttu-id="5a10f-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="5a10f-111">4.5.2</span></span>|
|<span data-ttu-id="5a10f-112">Тип</span><span class="sxs-lookup"><span data-stu-id="5a10f-112">Type</span></span>|<span data-ttu-id="5a10f-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="5a10f-113">Runtime</span></span>|
|<span data-ttu-id="5a10f-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5a10f-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
