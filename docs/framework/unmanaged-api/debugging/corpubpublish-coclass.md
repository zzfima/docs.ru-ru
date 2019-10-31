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
ms.openlocfilehash: 89af99fab1f1265701e0dbfe74a46000cb3bfaa6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132149"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="75d3a-102">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="75d3a-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="75d3a-103">Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.</span><span class="sxs-lookup"><span data-stu-id="75d3a-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75d3a-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="75d3a-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="75d3a-105">Interfaces</span></span>  
  
|<span data-ttu-id="75d3a-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="75d3a-106">Interface</span></span>|<span data-ttu-id="75d3a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="75d3a-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="75d3a-108">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="75d3a-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="75d3a-109">Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="75d3a-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="75d3a-110">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="75d3a-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="75d3a-111">Представляет и предоставляет сведения о домене приложения в процессе.</span><span class="sxs-lookup"><span data-stu-id="75d3a-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="75d3a-112">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="75d3a-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="75d3a-113">Предоставляет методы, которые проходят через коллекцию доменов приложений, которые в данный момент существуют в процессе.</span><span class="sxs-lookup"><span data-stu-id="75d3a-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="75d3a-114">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="75d3a-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="75d3a-115">Представляет процесс, выполняющийся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="75d3a-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="75d3a-116">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="75d3a-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="75d3a-117">Предоставляет методы, которые проходят по коллекции процессов, выполняющихся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="75d3a-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75d3a-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="75d3a-118">Remarks</span></span>  
 <span data-ttu-id="75d3a-119">Типичный сценарий публикации включает в себя разработчика, желающего отлаживать управляемый код, выполняющийся на компьютере в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="75d3a-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="75d3a-120">Среда размещения может запускать несколько доменов приложений в рамках одного процесса.</span><span class="sxs-lookup"><span data-stu-id="75d3a-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="75d3a-121">Разработчику хотелось бы использовать графический пользовательский интерфейс или другие средства для перечисления всех процессов, запущенных на компьютере, и выбрать конкретный процесс.</span><span class="sxs-lookup"><span data-stu-id="75d3a-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="75d3a-122">Список должен включать все домены приложений в процессах, выполняющих управляемый код.</span><span class="sxs-lookup"><span data-stu-id="75d3a-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="75d3a-123">Затем разработчик может определить конкретный домен приложения и подключить к этому домену отладчик.</span><span class="sxs-lookup"><span data-stu-id="75d3a-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75d3a-124">Требования</span><span class="sxs-lookup"><span data-stu-id="75d3a-124">Requirements</span></span>  
 <span data-ttu-id="75d3a-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75d3a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75d3a-126">**Заголовок:** Корпуб. idl</span><span class="sxs-lookup"><span data-stu-id="75d3a-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="75d3a-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75d3a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75d3a-128">**.NET Framework версии:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75d3a-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d3a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="75d3a-129">See also</span></span>

- [<span data-ttu-id="75d3a-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="75d3a-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
