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
ms.openlocfilehash: 014bd4f2b12c84790065f76a67765aaf35e8b2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131682"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="fbeb8-102">Метод IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="fbeb8-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="fbeb8-103">Возвращает указатель на структуру [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) , представленную этим объектом [IInstallReferenceItem](iinstallreferenceitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fbeb8-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbeb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbeb8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbeb8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbeb8-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="fbeb8-106">заполняет Возвращаемый указатель `FUSION_INSTALL_REFERENCE`.</span><span class="sxs-lookup"><span data-stu-id="fbeb8-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fbeb8-107">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="fbeb8-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fbeb8-108">значение `dwFlags` должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="fbeb8-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fbeb8-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="fbeb8-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fbeb8-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="fbeb8-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbeb8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fbeb8-111">Requirements</span></span>  
 <span data-ttu-id="fbeb8-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbeb8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbeb8-113">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fbeb8-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fbeb8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbeb8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbeb8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fbeb8-115">See also</span></span>

- [<span data-ttu-id="fbeb8-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="fbeb8-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="fbeb8-117">Структура FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="fbeb8-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
