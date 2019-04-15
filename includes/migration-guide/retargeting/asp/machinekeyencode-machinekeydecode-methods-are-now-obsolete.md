---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234797"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="0c34f-101">Методы MachineKey.Encode и MachineKey.Decode устарели</span><span class="sxs-lookup"><span data-stu-id="0c34f-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0c34f-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0c34f-102">Details</span></span>|<span data-ttu-id="0c34f-103">В настоящее время эти методы считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="0c34f-103">These methods are now obsolete.</span></span> <span data-ttu-id="0c34f-104">При компиляции кода, который вызывает эти методы, создается предупреждение компилятора.</span><span class="sxs-lookup"><span data-stu-id="0c34f-104">Compilation of code that calls these methods produces a compiler warning.</span></span>|
|<span data-ttu-id="0c34f-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0c34f-105">Suggestion</span></span>|<span data-ttu-id="0c34f-106">Взамен рекомендуется использовать <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> и <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="0c34f-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="0c34f-107">Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="0c34f-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="0c34f-108">Интерфейсы API по-прежнему поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0c34f-108">The APIs are still supported.</span></span>|
|<span data-ttu-id="0c34f-109">Область</span><span class="sxs-lookup"><span data-stu-id="0c34f-109">Scope</span></span>|<span data-ttu-id="0c34f-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="0c34f-110">Minor</span></span>|
|<span data-ttu-id="0c34f-111">Версия</span><span class="sxs-lookup"><span data-stu-id="0c34f-111">Version</span></span>|<span data-ttu-id="0c34f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0c34f-112">4.5</span></span>|
|<span data-ttu-id="0c34f-113">Тип</span><span class="sxs-lookup"><span data-stu-id="0c34f-113">Type</span></span>|<span data-ttu-id="0c34f-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="0c34f-114">Retargeting</span></span>|
|<span data-ttu-id="0c34f-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0c34f-115">Affected APIs</span></span>|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
