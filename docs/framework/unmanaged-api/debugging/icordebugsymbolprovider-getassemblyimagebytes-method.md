---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageBytes
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103e724c37ae356729dd5bba3ff66c0f443f6eaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170239"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="e60ab-102">Метод ICorDebugSymbolProvider::GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="e60ab-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="e60ab-103">Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="e60ab-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e60ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e60ab-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e60ab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e60ab-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="e60ab-106">[in] Относительный виртуальный адрес (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="e60ab-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="e60ab-107">Число байт для чтения из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="e60ab-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="e60ab-108">Указатель на адрес [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) , содержащий сведения о буфере памяти с метаданными объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="e60ab-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e60ab-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e60ab-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e60ab-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e60ab-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e60ab-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e60ab-111">Requirements</span></span>  
 <span data-ttu-id="e60ab-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e60ab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e60ab-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e60ab-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e60ab-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e60ab-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e60ab-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e60ab-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e60ab-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e60ab-116">See also</span></span>

- [<span data-ttu-id="e60ab-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="e60ab-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e60ab-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e60ab-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
