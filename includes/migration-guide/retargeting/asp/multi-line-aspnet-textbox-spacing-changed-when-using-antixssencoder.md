---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774449"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="ce386-101">Изменены интервалы многострочного текстового поля ASP.NET при использовании AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="ce386-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ce386-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ce386-102">Details</span></span>|<span data-ttu-id="ce386-103">В .NET Framework 4.0 между строками многострочного текстового поля при обратной передаче вставлялись дополнительные строки, если использовался <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="ce386-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span></span> <span data-ttu-id="ce386-104">В .NET Framework 4.5 эти дополнительные разрывы строк отсутствуют только в том случае, если веб-приложение предназначено для .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ce386-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>|
|<span data-ttu-id="ce386-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="ce386-105">Suggestion</span></span>|<span data-ttu-id="ce386-106">Имейте в виду, что в веб-приложениях 4.0, перенаправленных на .NET Framework 4.5, многострочные текстовые поля могут быть усовершенствованы, чтобы больше не вставлять дополнительные разрывы строк.</span><span class="sxs-lookup"><span data-stu-id="ce386-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="ce386-107">Если это нежелательно, для приложения, выполняющегося в .NET Framework 4.5, можно сохранить старое поведение путем изменения версии платформы на .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="ce386-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>|
|<span data-ttu-id="ce386-108">Область</span><span class="sxs-lookup"><span data-stu-id="ce386-108">Scope</span></span>|<span data-ttu-id="ce386-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ce386-109">Minor</span></span>|
|<span data-ttu-id="ce386-110">Версия</span><span class="sxs-lookup"><span data-stu-id="ce386-110">Version</span></span>|<span data-ttu-id="ce386-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ce386-111">4.5</span></span>|
|<span data-ttu-id="ce386-112">Тип</span><span class="sxs-lookup"><span data-stu-id="ce386-112">Type</span></span>|<span data-ttu-id="ce386-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ce386-113">Retargeting</span></span>|
