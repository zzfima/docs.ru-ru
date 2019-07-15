---
ms.openlocfilehash: 8d058d3297471e67459164f18358b1d143465712
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803238"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="db8e5-101">ASP.NET MVC теперь экранирует пробелы в строках, переданных через параметры маршрута</span><span class="sxs-lookup"><span data-stu-id="db8e5-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="db8e5-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="db8e5-102">Details</span></span>|<span data-ttu-id="db8e5-103">Чтобы соответствовать стандарту RFC 2396, пробелы в путях маршрута теперь экранируются при заполнении параметров действий из маршрута.</span><span class="sxs-lookup"><span data-stu-id="db8e5-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="db8e5-104">Таким образом, в то время как <code>/controller/action/some data</code> ранее соответствовал маршруту <code>/controller/action/{data}</code> и предоставлял <code>some data</code> в качестве параметра данных, теперь он будет предоставлять <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="db8e5-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="db8e5-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="db8e5-105">Suggestion</span></span>|<span data-ttu-id="db8e5-106">Код должен быть обновлен для неэкранирования строковых параметров из маршрута.</span><span class="sxs-lookup"><span data-stu-id="db8e5-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="db8e5-107">Если необходим исходный URI, доступ к нему можно получить с помощью API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="db8e5-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="db8e5-108">Область</span><span class="sxs-lookup"><span data-stu-id="db8e5-108">Scope</span></span>|<span data-ttu-id="db8e5-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="db8e5-109">Minor</span></span>|
|<span data-ttu-id="db8e5-110">Версия</span><span class="sxs-lookup"><span data-stu-id="db8e5-110">Version</span></span>|<span data-ttu-id="db8e5-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="db8e5-111">4.5.2</span></span>|
|<span data-ttu-id="db8e5-112">Тип</span><span class="sxs-lookup"><span data-stu-id="db8e5-112">Type</span></span>|<span data-ttu-id="db8e5-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="db8e5-113">Runtime</span></span>|
|<span data-ttu-id="db8e5-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="db8e5-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|

