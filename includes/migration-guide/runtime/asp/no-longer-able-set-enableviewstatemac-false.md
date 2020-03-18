---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803246"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="5012d-101">Свойству EnableViewStateMac больше невозможно задавать значение false</span><span class="sxs-lookup"><span data-stu-id="5012d-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5012d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5012d-102">Details</span></span>|<span data-ttu-id="5012d-103">ASP.NET теперь не позволяет разработчикам указывать <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> или <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="5012d-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="5012d-104">Код проверки подлинности сообщения (MAC) состояния просмотра теперь принудительно применяется для всех запросов со встроенным состоянием просмотра.</span><span class="sxs-lookup"><span data-stu-id="5012d-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="5012d-105">Затрагиваются только те приложения, в которых для свойства EnableViewStateMac явно задано значение <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="5012d-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="5012d-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="5012d-106">Suggestion</span></span>|<span data-ttu-id="5012d-107">Следует считать, что свойство EnableViewStateMac имеет значение true, и возникающие ошибки MAC должны быть устранены (как описано в [этом](https://support.microsoft.com/kb/2915218) руководстве, содержащем несколько решений в зависимости от причины ошибки MAC).</span><span class="sxs-lookup"><span data-stu-id="5012d-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="5012d-108">Область</span><span class="sxs-lookup"><span data-stu-id="5012d-108">Scope</span></span>|<span data-ttu-id="5012d-109">Значительно</span><span class="sxs-lookup"><span data-stu-id="5012d-109">Major</span></span>|
|<span data-ttu-id="5012d-110">Version</span><span class="sxs-lookup"><span data-stu-id="5012d-110">Version</span></span>|<span data-ttu-id="5012d-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="5012d-111">4.5.2</span></span>|
|<span data-ttu-id="5012d-112">Type</span><span class="sxs-lookup"><span data-stu-id="5012d-112">Type</span></span>|<span data-ttu-id="5012d-113">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="5012d-113">Runtime</span></span>|
