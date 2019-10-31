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
ms.openlocfilehash: 0dad50f1acac38f8cdc505026e88d42882deb580
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131725"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="95e95-102">Метод IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="95e95-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="95e95-103">Возвращает указатель на следующий объект [IInstallReferenceItem](iinstallreferenceitem-interface.md) , содержащийся в этом объекте [IInstallReferenceEnum](iinstallreferenceenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="95e95-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95e95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e95-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95e95-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="95e95-106">заполняет Возвращаемый указатель `IInstallReferenceItem`.</span><span class="sxs-lookup"><span data-stu-id="95e95-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="95e95-107">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="95e95-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="95e95-108">значение `dwFlags` должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="95e95-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="95e95-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="95e95-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="95e95-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="95e95-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e95-111">Требования</span><span class="sxs-lookup"><span data-stu-id="95e95-111">Requirements</span></span>  
 <span data-ttu-id="95e95-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e95-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e95-113">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="95e95-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="95e95-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e95-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e95-115">См. также</span><span class="sxs-lookup"><span data-stu-id="95e95-115">See also</span></span>

- [<span data-ttu-id="95e95-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="95e95-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="95e95-117">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="95e95-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
