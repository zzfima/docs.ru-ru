---
title: 'Метод метод icordebugsymbolprovider:: Жетассемблимажебитес'
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 3184ba116704df8945b53766e62435a4252eaa11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138938"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="62503-102">Метод метод icordebugsymbolprovider:: Жетассемблимажебитес</span><span class="sxs-lookup"><span data-stu-id="62503-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="62503-103">Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="62503-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62503-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62503-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62503-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62503-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="62503-106">[in] Относительный виртуальный адрес (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="62503-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="62503-107">Число байт для чтения из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="62503-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="62503-108">Указатель на адрес объекта [икордебугмеморибуффер](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) , который содержит сведения о буфере памяти с объединенными метаданными сборки.</span><span class="sxs-lookup"><span data-stu-id="62503-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62503-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="62503-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62503-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="62503-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62503-111">Требования</span><span class="sxs-lookup"><span data-stu-id="62503-111">Requirements</span></span>  
 <span data-ttu-id="62503-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62503-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62503-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62503-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62503-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62503-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62503-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62503-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62503-116">См. также</span><span class="sxs-lookup"><span data-stu-id="62503-116">See also</span></span>

- [<span data-ttu-id="62503-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="62503-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="62503-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="62503-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
