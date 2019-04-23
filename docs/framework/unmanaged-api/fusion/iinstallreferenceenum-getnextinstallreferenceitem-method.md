---
title: Метод IInstallReferenceEnum::GetNextInstallReferenceItem
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc04bb12e4271a3237ebef140c481620fc01ad7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202382"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="8be33-102">Метод IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="8be33-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="8be33-103">Получает указатель на следующий [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) объект, содержащийся в этом [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="8be33-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8be33-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8be33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8be33-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="8be33-106">[out] Возвращенный `IInstallReferenceItem` указатель.</span><span class="sxs-lookup"><span data-stu-id="8be33-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8be33-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="8be33-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8be33-108">`dwFlags` должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="8be33-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8be33-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="8be33-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8be33-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="8be33-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be33-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8be33-111">Requirements</span></span>  
 <span data-ttu-id="8be33-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8be33-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be33-113">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8be33-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8be33-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be33-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be33-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8be33-115">See also</span></span>

- [<span data-ttu-id="8be33-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="8be33-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="8be33-117">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="8be33-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
