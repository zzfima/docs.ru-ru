---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235928"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="16b72-101">Метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда</span><span class="sxs-lookup"><span data-stu-id="16b72-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

|   |   |
|---|---|
|<span data-ttu-id="16b72-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="16b72-102">Details</span></span>|<span data-ttu-id="16b72-103">Начиная с версии .NET Framework 4.5, метод <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> экранирует символ амперсанда (&amp;).</span><span class="sxs-lookup"><span data-stu-id="16b72-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> escapes the ampersand (&amp;) character.</span></span>|
|<span data-ttu-id="16b72-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="16b72-104">Suggestion</span></span>|<span data-ttu-id="16b72-105">Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="16b72-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>|
|<span data-ttu-id="16b72-106">Область</span><span class="sxs-lookup"><span data-stu-id="16b72-106">Scope</span></span>|<span data-ttu-id="16b72-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="16b72-107">Minor</span></span>|
|<span data-ttu-id="16b72-108">Версия</span><span class="sxs-lookup"><span data-stu-id="16b72-108">Version</span></span>|<span data-ttu-id="16b72-109">4.5</span><span class="sxs-lookup"><span data-stu-id="16b72-109">4.5</span></span>|
|<span data-ttu-id="16b72-110">Тип</span><span class="sxs-lookup"><span data-stu-id="16b72-110">Type</span></span>|<span data-ttu-id="16b72-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="16b72-111">Runtime</span></span>|
|<span data-ttu-id="16b72-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="16b72-112">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
