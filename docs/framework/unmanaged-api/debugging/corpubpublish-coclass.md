---
title: "Компонентный класс CorpubPublish"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c1565c9321e64536139e02b239fbeb4247a58a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="adc93-102">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="adc93-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="adc93-103">Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.</span><span class="sxs-lookup"><span data-stu-id="adc93-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adc93-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="adc93-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="adc93-105">Interfaces</span></span>  
  
|<span data-ttu-id="adc93-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="adc93-106">Interface</span></span>|<span data-ttu-id="adc93-107">Описание</span><span class="sxs-lookup"><span data-stu-id="adc93-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="adc93-108">ICorPublish-интерфейс</span><span class="sxs-lookup"><span data-stu-id="adc93-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="adc93-109">Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессов.</span><span class="sxs-lookup"><span data-stu-id="adc93-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="adc93-110">ICorPublishAppDomain-интерфейс</span><span class="sxs-lookup"><span data-stu-id="adc93-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="adc93-111">Представляет и предоставляет сведения о домен приложения в процессе.</span><span class="sxs-lookup"><span data-stu-id="adc93-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="adc93-112">ICorPublishAppDomainEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="adc93-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="adc93-113">Предоставляет методы, выполняющие перебор коллекции доменов приложений, которые в настоящее время существует внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="adc93-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="adc93-114">ICorPublishProcess-интерфейс</span><span class="sxs-lookup"><span data-stu-id="adc93-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="adc93-115">Представляет процесс, который выполняется на компьютере.</span><span class="sxs-lookup"><span data-stu-id="adc93-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="adc93-116">ICorPublishProcessEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="adc93-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="adc93-117">Предоставляет методы, выполняющие перебор коллекции процессов, запущенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="adc93-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adc93-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="adc93-118">Remarks</span></span>  
 <span data-ttu-id="adc93-119">Типичный сценарий публикации подразумевает разработчик, которому необходимо произвести отладку управляемого кода, запущенного на компьютере в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="adc93-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="adc93-120">Среда размещения может выполняться несколько доменов приложений внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="adc93-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="adc93-121">Разработчик хотел бы использовать графический пользовательский интерфейс или другими средствами, чтобы получить список всех процессов, запущенных на компьютере и выбирать процессы.</span><span class="sxs-lookup"><span data-stu-id="adc93-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="adc93-122">Список должен включать всех доменов приложений внутри процессов, запущенных в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="adc93-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="adc93-123">Разработчик можно определить домен определенное приложение и подключить отладчик к этому домену.</span><span class="sxs-lookup"><span data-stu-id="adc93-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adc93-124">Требования</span><span class="sxs-lookup"><span data-stu-id="adc93-124">Requirements</span></span>  
 <span data-ttu-id="adc93-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adc93-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc93-126">**Заголовок:** CorPub.idl</span><span class="sxs-lookup"><span data-stu-id="adc93-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="adc93-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adc93-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adc93-128">**Версии платформы .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adc93-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc93-129">См. также</span><span class="sxs-lookup"><span data-stu-id="adc93-129">See Also</span></span>  
 [<span data-ttu-id="adc93-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="adc93-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
