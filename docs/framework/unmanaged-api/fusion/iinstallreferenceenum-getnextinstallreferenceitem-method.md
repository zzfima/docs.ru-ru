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
ms.openlocfilehash: 20e2bff4257df64f761fd8fff880643d4e786748
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796448"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="02514-102">Метод IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="02514-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="02514-103">Возвращает указатель на следующий объект [IInstallReferenceItem](iinstallreferenceitem-interface.md) , содержащийся в этом объекте [IInstallReferenceEnum](iinstallreferenceenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="02514-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02514-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02514-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02514-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02514-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="02514-106">заполняет Возвращаемый `IInstallReferenceItem` указатель.</span><span class="sxs-lookup"><span data-stu-id="02514-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="02514-107">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="02514-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="02514-108">`dwFlags`значение должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="02514-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="02514-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="02514-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="02514-110">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="02514-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02514-111">Требования</span><span class="sxs-lookup"><span data-stu-id="02514-111">Requirements</span></span>  
 <span data-ttu-id="02514-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02514-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02514-113">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="02514-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="02514-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02514-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02514-115">См. также</span><span class="sxs-lookup"><span data-stu-id="02514-115">See also</span></span>

- [<span data-ttu-id="02514-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="02514-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="02514-117">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="02514-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
