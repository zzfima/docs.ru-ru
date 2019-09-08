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
ms.openlocfilehash: 9395fcc6d896114c25770edbc17761323285099f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796394"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="50c3b-102">Метод IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="50c3b-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="50c3b-103">Возвращает указатель на структуру [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) , представленную этим объектом [IInstallReferenceItem](iinstallreferenceitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="50c3b-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50c3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50c3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50c3b-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="50c3b-106">заполняет Возвращаемый `FUSION_INSTALL_REFERENCE` указатель.</span><span class="sxs-lookup"><span data-stu-id="50c3b-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="50c3b-107">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="50c3b-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="50c3b-108">`dwFlags`значение должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="50c3b-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="50c3b-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="50c3b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="50c3b-110">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="50c3b-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c3b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="50c3b-111">Requirements</span></span>  
 <span data-ttu-id="50c3b-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50c3b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c3b-113">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="50c3b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="50c3b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c3b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c3b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="50c3b-115">See also</span></span>

- [<span data-ttu-id="50c3b-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="50c3b-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="50c3b-117">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="50c3b-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
