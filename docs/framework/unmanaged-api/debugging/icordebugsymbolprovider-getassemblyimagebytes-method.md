---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageBytes
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aaecbe3640e5da78c13a077611887c6b62d355a4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771512"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="dc442-102">Метод ICorDebugSymbolProvider::GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="dc442-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="dc442-103">Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="dc442-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc442-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc442-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc442-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc442-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="dc442-106">[in] Относительный виртуальный адрес (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="dc442-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="dc442-107">Число байт для чтения из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="dc442-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="dc442-108">Указатель на адрес [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) , содержащий сведения о буфере памяти с метаданными объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="dc442-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc442-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc442-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc442-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="dc442-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc442-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dc442-111">Requirements</span></span>  
 <span data-ttu-id="dc442-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc442-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc442-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc442-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc442-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc442-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc442-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc442-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc442-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dc442-116">See also</span></span>

- [<span data-ttu-id="dc442-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="dc442-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="dc442-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dc442-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
