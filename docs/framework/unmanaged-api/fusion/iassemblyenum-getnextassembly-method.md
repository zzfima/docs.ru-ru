---
title: Метод IAssemblyEnum::GetNextAssembly
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39e6cbdf683ad59be93c88d87ba7a7194ac83992
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502401"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="4f687-102">Метод IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="4f687-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="4f687-103">Получает указатель на следующий [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) , содержащихся в данном [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="4f687-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f687-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f687-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f687-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f687-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="4f687-106">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="4f687-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4f687-107">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="4f687-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="4f687-108">[out] Возвращенный `IAssemblyName` указатель.</span><span class="sxs-lookup"><span data-stu-id="4f687-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4f687-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="4f687-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4f687-110">`dwFlags` должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="4f687-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f687-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4f687-111">Requirements</span></span>  
 <span data-ttu-id="4f687-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f687-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f687-113">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4f687-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4f687-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f687-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f687-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4f687-115">See also</span></span>
- [<span data-ttu-id="4f687-116">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="4f687-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="4f687-117">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="4f687-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
