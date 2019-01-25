---
title: Интерфейс ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19bd34f95e17094a89e4929a5b6ae936afe39885
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531919"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="2bd20-102">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="2bd20-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="2bd20-103">Предоставляет методы, которые обращаются к сведений, отображаемый о процессе.</span><span class="sxs-lookup"><span data-stu-id="2bd20-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2bd20-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2bd20-104">Methods</span></span>  
  
|<span data-ttu-id="2bd20-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2bd20-105">Method</span></span>|<span data-ttu-id="2bd20-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2bd20-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2bd20-107">Метод EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="2bd20-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="2bd20-108">Получает [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) экземпляр, содержащий домены приложений в процессе, который ссылается этот `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="2bd20-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="2bd20-109">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="2bd20-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="2bd20-110">Возвращает полный путь к исполняемому файлу для процесса, который ссылается этот `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="2bd20-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="2bd20-111">Метод GetProcessID</span><span class="sxs-lookup"><span data-stu-id="2bd20-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="2bd20-112">Получает идентификатор операционной системы для процесса, который ссылается этот `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="2bd20-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="2bd20-113">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="2bd20-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="2bd20-114">Получает значение, указывающее, является ли процесс ссылается этот `ICorPublishProcess` известен выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2bd20-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2bd20-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2bd20-115">Requirements</span></span>  
 <span data-ttu-id="2bd20-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bd20-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bd20-117">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2bd20-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2bd20-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bd20-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bd20-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd20-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd20-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2bd20-120">See also</span></span>
- [<span data-ttu-id="2bd20-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2bd20-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2bd20-122">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="2bd20-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
