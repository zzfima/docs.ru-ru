---
title: "Метод IInstallReferenceEnum::GetNextInstallReferenceItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum.GetNextInstallReferenceItem
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f3a1b745c3ee28c126e328b1a3fa9e283f98d99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="ebc3b-102">Метод IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="ebc3b-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="ebc3b-103">Возвращает указатель на следующий [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) объектов, содержащихся в этом [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="ebc3b-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebc3b-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebc3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebc3b-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="ebc3b-106">[out] Возвращенный `IInstallReferenceItem` указателя.</span><span class="sxs-lookup"><span data-stu-id="ebc3b-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ebc3b-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="ebc3b-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ebc3b-108">`dwFlags`должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="ebc3b-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ebc3b-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="ebc3b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ebc3b-110">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="ebc3b-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc3b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ebc3b-111">Requirements</span></span>  
 <span data-ttu-id="ebc3b-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebc3b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc3b-113">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ebc3b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ebc3b-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc3b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc3b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ebc3b-115">See Also</span></span>  
 [<span data-ttu-id="ebc3b-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="ebc3b-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="ebc3b-117">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="ebc3b-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
