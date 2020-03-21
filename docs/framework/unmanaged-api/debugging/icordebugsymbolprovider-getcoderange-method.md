---
title: Метод ICorDebugSymbolProvider::GetCodeRange
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: 81babade2ba499ce9326c664e83fa582abbd216f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178470"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="a709b-102">Метод ICorDebugSymbolProvider::GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="a709b-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="a709b-103">Получает начальный адрес метода и размер для указанного относительного виртуального адреса (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="a709b-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a709b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a709b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,
   [out] ULONG32* pCodeStartAddress,
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a709b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a709b-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="a709b-106">[in] Относительный виртуальный адрес (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="a709b-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="a709b-107">[out] Указатель на начальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="a709b-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="a709b-108">Указатель на размер кода метода (число байтов кода метода).</span><span class="sxs-lookup"><span data-stu-id="a709b-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a709b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a709b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a709b-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a709b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a709b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a709b-111">Requirements</span></span>  
 <span data-ttu-id="a709b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a709b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a709b-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a709b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a709b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a709b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a709b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a709b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a709b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a709b-116">See also</span></span>

- [<span data-ttu-id="a709b-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a709b-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a709b-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a709b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
