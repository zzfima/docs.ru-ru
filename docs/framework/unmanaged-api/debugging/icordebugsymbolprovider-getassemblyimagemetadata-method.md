---
title: Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cb255330937b00a987ee0d07f0332d04fe1746d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489986"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="a35b3-102">Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="a35b3-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="a35b3-103">Возвращает метаданные из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="a35b3-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a35b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a35b3-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a35b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a35b3-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="a35b3-106">[out] Указатель на адрес [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) объект, содержащий сведения о размере и адресе метаданных объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="a35b3-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a35b3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a35b3-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a35b3-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a35b3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a35b3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a35b3-109">Requirements</span></span>  
 <span data-ttu-id="a35b3-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a35b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a35b3-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a35b3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a35b3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a35b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a35b3-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a35b3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35b3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a35b3-114">See also</span></span>
- [<span data-ttu-id="a35b3-115">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a35b3-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a35b3-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a35b3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
