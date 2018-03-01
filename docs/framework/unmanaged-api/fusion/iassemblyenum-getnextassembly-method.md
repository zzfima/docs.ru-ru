---
title: "Метод IAssemblyEnum::GetNextAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2666970e220334e9e8c2470622026442db0c2f95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="2dc48-102">Метод IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="2dc48-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="2dc48-103">Возвращает указатель на следующий [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) , содержащихся в данном [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="2dc48-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dc48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dc48-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2dc48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2dc48-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="2dc48-106">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="2dc48-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="2dc48-107">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="2dc48-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="2dc48-108">[out] Возвращенный `IAssemblyName` указателя.</span><span class="sxs-lookup"><span data-stu-id="2dc48-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2dc48-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="2dc48-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="2dc48-110">`dwFlags`должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="2dc48-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dc48-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2dc48-111">Requirements</span></span>  
 <span data-ttu-id="2dc48-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dc48-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dc48-113">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="2dc48-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2dc48-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dc48-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc48-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2dc48-115">See Also</span></span>  
 [<span data-ttu-id="2dc48-116">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="2dc48-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="2dc48-117">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="2dc48-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
