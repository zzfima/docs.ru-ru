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
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757681"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="020a5-102">Метод IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="020a5-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="020a5-103">Возвращает указатель на [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) структуры, представленный этим [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="020a5-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="020a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="020a5-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="020a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="020a5-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="020a5-106">[out] Возвращенный `FUSION_INSTALL_REFERENCE` указатель.</span><span class="sxs-lookup"><span data-stu-id="020a5-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="020a5-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="020a5-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="020a5-108">`dwFlags` должно быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="020a5-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="020a5-109">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="020a5-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="020a5-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="020a5-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="020a5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="020a5-111">Requirements</span></span>  
 <span data-ttu-id="020a5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="020a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="020a5-113">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="020a5-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="020a5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="020a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020a5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="020a5-115">See also</span></span>

- [<span data-ttu-id="020a5-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="020a5-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="020a5-117">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="020a5-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
