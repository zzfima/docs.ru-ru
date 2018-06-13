---
title: Метод IInstallReferenceItem::GetReference
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6c64b98f3b5ab0445b076b0d3bacfaa398e26f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429772"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="04d7a-102">Метод IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="04d7a-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="04d7a-103">Возвращает указатель на [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) структуры, представленный этим [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="04d7a-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04d7a-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04d7a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04d7a-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="04d7a-106">[out] Возвращенный `FUSION_INSTALL_REFERENCE` указателя.</span><span class="sxs-lookup"><span data-stu-id="04d7a-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="04d7a-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="04d7a-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="04d7a-108">`dwFlags` должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="04d7a-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="04d7a-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="04d7a-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="04d7a-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="04d7a-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04d7a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="04d7a-111">Requirements</span></span>  
 <span data-ttu-id="04d7a-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04d7a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d7a-113">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="04d7a-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="04d7a-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04d7a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d7a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="04d7a-115">See Also</span></span>  
 [<span data-ttu-id="04d7a-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="04d7a-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="04d7a-117">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="04d7a-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
