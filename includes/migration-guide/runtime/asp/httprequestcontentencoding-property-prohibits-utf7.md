---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235430"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="2049f-101">Свойство HttpRequest.ContentEncoding запрещает кодировку UTF7</span><span class="sxs-lookup"><span data-stu-id="2049f-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2049f-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2049f-102">Details</span></span>|<span data-ttu-id="2049f-103">Начиная с .NET Framework 4.5 кодировка UTF-7 запрещена в теле <xref:System.Web.HttpRequest?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="2049f-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=name>s' bodies.</span></span> <span data-ttu-id="2049f-104">Данные для приложений, которые зависят от поступающих данных UTF-7, в некоторых случаях декодируются неверно.</span><span class="sxs-lookup"><span data-stu-id="2049f-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>|
|<span data-ttu-id="2049f-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="2049f-105">Suggestion</span></span>|<span data-ttu-id="2049f-106">В идеальном случае приложения необходимо обновить, чтобы они не использовали кодировку UTF-7 в <xref:System.Web.HttpRequest?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="2049f-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=name>s.</span></span> <span data-ttu-id="2049f-107">Кроме того, устаревшее поведение можно восстановить с помощью атрибута <code>aspnet:AllowUtf7RequestContentEncoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="2049f-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>|
|<span data-ttu-id="2049f-108">Область</span><span class="sxs-lookup"><span data-stu-id="2049f-108">Scope</span></span>|<span data-ttu-id="2049f-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="2049f-109">Edge</span></span>|
|<span data-ttu-id="2049f-110">Версия</span><span class="sxs-lookup"><span data-stu-id="2049f-110">Version</span></span>|<span data-ttu-id="2049f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="2049f-111">4.5</span></span>|
|<span data-ttu-id="2049f-112">Тип</span><span class="sxs-lookup"><span data-stu-id="2049f-112">Type</span></span>|<span data-ttu-id="2049f-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2049f-113">Runtime</span></span>|
|<span data-ttu-id="2049f-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2049f-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
