---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d96aa82e9fd8b651ab005cba4945f6977c1e3d3a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771506"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="6189c-102">Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="6189c-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="6189c-103">Возвращает метаданные из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="6189c-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6189c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6189c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6189c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6189c-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="6189c-106">[out] Указатель на адрес [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) объект, содержащий сведения о размере и адресе метаданных объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="6189c-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6189c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6189c-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6189c-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6189c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6189c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6189c-109">Requirements</span></span>  
 <span data-ttu-id="6189c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6189c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6189c-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6189c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6189c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6189c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6189c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6189c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6189c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6189c-114">See also</span></span>

- [<span data-ttu-id="6189c-115">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="6189c-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6189c-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6189c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
