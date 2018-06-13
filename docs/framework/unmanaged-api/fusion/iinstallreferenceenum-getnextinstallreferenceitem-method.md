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
ms.openlocfilehash: b756cdcbbc852280e88fef2d1a2bf5f0125cbd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429215"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="0027b-102">Метод IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="0027b-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="0027b-103">Возвращает указатель на следующий [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) объектов, содержащихся в этом [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="0027b-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0027b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0027b-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0027b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0027b-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="0027b-106">[out] Возвращенный `IInstallReferenceItem` указателя.</span><span class="sxs-lookup"><span data-stu-id="0027b-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0027b-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="0027b-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="0027b-108">`dwFlags` должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="0027b-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="0027b-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="0027b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="0027b-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="0027b-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0027b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0027b-111">Requirements</span></span>  
 <span data-ttu-id="0027b-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0027b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0027b-113">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0027b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0027b-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0027b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0027b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0027b-115">See Also</span></span>  
 [<span data-ttu-id="0027b-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="0027b-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="0027b-117">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="0027b-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
