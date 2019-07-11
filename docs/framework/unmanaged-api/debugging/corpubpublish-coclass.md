---
title: Кокласс CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d1ca8ea9d00de8a07c67977cf108c50268802e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739354"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="1bc49-102">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="1bc49-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="1bc49-103">Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.</span><span class="sxs-lookup"><span data-stu-id="1bc49-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc49-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bc49-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="1bc49-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="1bc49-105">Interfaces</span></span>  
  
|<span data-ttu-id="1bc49-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="1bc49-106">Interface</span></span>|<span data-ttu-id="1bc49-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1bc49-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="1bc49-108">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="1bc49-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="1bc49-109">Предоставляет методы для публикации информации о процессах и домены приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="1bc49-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="1bc49-110">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="1bc49-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="1bc49-111">Представляет и предоставляет сведения о домене приложения в процессе.</span><span class="sxs-lookup"><span data-stu-id="1bc49-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="1bc49-112">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="1bc49-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="1bc49-113">Предоставляет методы, выполняющие перебор коллекции доменов приложений, которые в настоящее время существует внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="1bc49-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="1bc49-114">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="1bc49-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="1bc49-115">Представляет процесс, который выполняется на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1bc49-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="1bc49-116">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="1bc49-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="1bc49-117">Предоставляет методы, выполняющие перебор коллекции процессов, запущенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1bc49-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bc49-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bc49-118">Remarks</span></span>  
 <span data-ttu-id="1bc49-119">Типичный сценарий публикации включает в себя разработчик, которому необходимо произвести отладку управляемого кода, на котором выполняется на компьютере в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="1bc49-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="1bc49-120">Среда размещения может выполняться несколько доменов приложений внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="1bc49-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="1bc49-121">Разработчик хотел использовать графический пользовательский интерфейс или другими средствами, чтобы получить список всех процессов, запущенных на компьютере, а затем выбрать определенный процесс.</span><span class="sxs-lookup"><span data-stu-id="1bc49-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="1bc49-122">Список должен включать все домены приложений в процессы, работающие в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="1bc49-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="1bc49-123">Разработчик можно определить домен определенное приложение и подключить отладчик к этому домену.</span><span class="sxs-lookup"><span data-stu-id="1bc49-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bc49-124">Требования</span><span class="sxs-lookup"><span data-stu-id="1bc49-124">Requirements</span></span>  
 <span data-ttu-id="1bc49-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bc49-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bc49-126">**Заголовок.** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="1bc49-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="1bc49-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bc49-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bc49-128">**Версии платформы .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bc49-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc49-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1bc49-129">See also</span></span>

- [<span data-ttu-id="1bc49-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="1bc49-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
