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
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182966"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="93af3-102">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="93af3-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="93af3-103">Предоставляет методы, которые обращаются к сведений, отображаемый о процессе.</span><span class="sxs-lookup"><span data-stu-id="93af3-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93af3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="93af3-104">Methods</span></span>  
  
|<span data-ttu-id="93af3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="93af3-105">Method</span></span>|<span data-ttu-id="93af3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="93af3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93af3-107">Метод EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="93af3-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="93af3-108">Получает [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) экземпляр, содержащий домены приложений в процессе, который ссылается этот `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="93af3-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="93af3-109">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="93af3-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="93af3-110">Возвращает полный путь к исполняемому файлу для процесса, который ссылается этот `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="93af3-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="93af3-111">Метод GetProcessID</span><span class="sxs-lookup"><span data-stu-id="93af3-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="93af3-112">Получает идентификатор операционной системы для процесса, который ссылается этот `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="93af3-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="93af3-113">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="93af3-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="93af3-114">Получает значение, указывающее, является ли процесс ссылается этот `ICorPublishProcess` известен выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="93af3-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93af3-115">Требования</span><span class="sxs-lookup"><span data-stu-id="93af3-115">Requirements</span></span>  
 <span data-ttu-id="93af3-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93af3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93af3-117">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="93af3-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="93af3-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93af3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93af3-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93af3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93af3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="93af3-120">See also</span></span>

- [<span data-ttu-id="93af3-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="93af3-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="93af3-122">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="93af3-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
