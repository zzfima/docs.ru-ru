---
title: 'Метод метод icordebugsymbolprovider:: GetCodeRange'
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: 84bf545fedf3a6c7915d94fd0c2630268585b6eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138924"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="b85e6-102">Метод метод icordebugsymbolprovider:: GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="b85e6-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="b85e6-103">Получает начальный адрес метода и размер для указанного относительного виртуального адреса (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="b85e6-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b85e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b85e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b85e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b85e6-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="b85e6-106">[in] Относительный виртуальный адрес (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="b85e6-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="b85e6-107">[out] Указатель на начальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="b85e6-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="b85e6-108">Указатель на размер кода метода (число байтов кода метода).</span><span class="sxs-lookup"><span data-stu-id="b85e6-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b85e6-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="b85e6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b85e6-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b85e6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b85e6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b85e6-111">Requirements</span></span>  
 <span data-ttu-id="b85e6-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b85e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b85e6-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b85e6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b85e6-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b85e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b85e6-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b85e6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85e6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b85e6-116">See also</span></span>

- [<span data-ttu-id="b85e6-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="b85e6-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b85e6-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b85e6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
