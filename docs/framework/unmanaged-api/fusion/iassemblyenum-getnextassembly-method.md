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
ms.openlocfilehash: 73c531378355100fdfca264ea9f96ff4d7c7ceda
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796687"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="78401-102">Метод IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="78401-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="78401-103">Возвращает указатель на следующее значение [IAssemblyName](iassemblyname-interface.md) , содержащееся в этом объекте [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="78401-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78401-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78401-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78401-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78401-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="78401-106">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="78401-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="78401-107">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="78401-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="78401-108">заполняет Возвращаемый `IAssemblyName` указатель.</span><span class="sxs-lookup"><span data-stu-id="78401-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="78401-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="78401-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="78401-110">`dwFlags`значение должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="78401-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78401-111">Требования</span><span class="sxs-lookup"><span data-stu-id="78401-111">Requirements</span></span>  
 <span data-ttu-id="78401-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78401-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78401-113">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="78401-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="78401-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78401-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78401-115">См. также</span><span class="sxs-lookup"><span data-stu-id="78401-115">See also</span></span>

- [<span data-ttu-id="78401-116">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="78401-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="78401-117">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="78401-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
