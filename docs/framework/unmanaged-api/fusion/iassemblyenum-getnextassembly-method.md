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
ms.openlocfilehash: ade404557d65fa073b6a0e66fe8234b41223ecde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134440"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="33b2b-102">Метод IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="33b2b-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="33b2b-103">Возвращает указатель на следующее значение [IAssemblyName](iassemblyname-interface.md) , содержащееся в этом объекте [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="33b2b-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33b2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33b2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33b2b-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="33b2b-106">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="33b2b-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="33b2b-107">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="33b2b-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="33b2b-108">заполняет Возвращаемый указатель `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="33b2b-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="33b2b-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="33b2b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="33b2b-110">значение `dwFlags` должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="33b2b-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33b2b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="33b2b-111">Requirements</span></span>  
 <span data-ttu-id="33b2b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33b2b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33b2b-113">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="33b2b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="33b2b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33b2b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b2b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="33b2b-115">See also</span></span>

- [<span data-ttu-id="33b2b-116">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="33b2b-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="33b2b-117">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="33b2b-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
