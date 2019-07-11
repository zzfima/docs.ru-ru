---
title: Метод ICorDebugSymbolProvider::GetCodeRange
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6d1f2bd903124773eaa20581f013bb41cf9cf99
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771485"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="fb276-102">Метод ICorDebugSymbolProvider::GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="fb276-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="fb276-103">Получает начальный адрес метода и размер для указанного относительного виртуального адреса (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="fb276-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb276-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb276-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb276-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb276-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="fb276-106">[in] Относительный виртуальный адрес (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="fb276-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="fb276-107">[out] Указатель на начальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="fb276-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="fb276-108">Указатель на размер кода метода (число байтов кода метода).</span><span class="sxs-lookup"><span data-stu-id="fb276-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb276-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb276-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb276-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="fb276-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb276-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fb276-111">Requirements</span></span>  
 <span data-ttu-id="fb276-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb276-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb276-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb276-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb276-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb276-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb276-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb276-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb276-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fb276-116">See also</span></span>

- [<span data-ttu-id="fb276-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="fb276-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="fb276-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fb276-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
