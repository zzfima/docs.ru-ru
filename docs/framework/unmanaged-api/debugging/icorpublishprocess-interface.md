---
title: "Интерфейс ICorPublishProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess
helpviewer_keywords: ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765be4e0ae7657d169ea561bc6a36bcf8cc11153
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="52ce5-102">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="52ce5-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="52ce5-103">Предоставляет методы, доступ к данным для отображения о процессе.</span><span class="sxs-lookup"><span data-stu-id="52ce5-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52ce5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="52ce5-104">Methods</span></span>  
  
|<span data-ttu-id="52ce5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="52ce5-105">Method</span></span>|<span data-ttu-id="52ce5-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="52ce5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52ce5-107">Метод EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="52ce5-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="52ce5-108">Возвращает [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) экземпляру, содержащему доменов приложений в процессе, упоминаемой в этом `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="52ce5-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="52ce5-109">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="52ce5-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="52ce5-110">Получает полный путь к исполняемому файлу процесса ссылается этот `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="52ce5-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="52ce5-111">Метод GetProcessID</span><span class="sxs-lookup"><span data-stu-id="52ce5-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="52ce5-112">Получает идентификатор операционной системы для процесса, упоминаемой в этом `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="52ce5-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="52ce5-113">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="52ce5-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="52ce5-114">Возвращает значение, указывающее, является ли процесс ссылается этот `ICorPublishProcess` известен выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="52ce5-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52ce5-115">Требования</span><span class="sxs-lookup"><span data-stu-id="52ce5-115">Requirements</span></span>  
 <span data-ttu-id="52ce5-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52ce5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52ce5-117">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="52ce5-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="52ce5-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52ce5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52ce5-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52ce5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ce5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="52ce5-120">See Also</span></span>  
 [<span data-ttu-id="52ce5-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="52ce5-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="52ce5-122">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="52ce5-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
