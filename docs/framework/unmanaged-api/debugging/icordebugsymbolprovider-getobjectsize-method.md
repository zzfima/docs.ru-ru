---
title: Метод ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10374f76edb9446093b89d064570ce05193129b3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498332"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="9d6b2-102">Метод ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="9d6b2-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="9d6b2-103">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="9d6b2-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d6b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d6b2-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d6b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d6b2-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="9d6b2-106">[in] Число байтов в сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="9d6b2-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="9d6b2-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="9d6b2-107">typeSig</span></span>  
 <span data-ttu-id="9d6b2-108">[в] Сигнатура TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="9d6b2-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="9d6b2-109">[out] Указатель на размер объекта.</span><span class="sxs-lookup"><span data-stu-id="9d6b2-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d6b2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d6b2-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d6b2-111">Этот метод доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9d6b2-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d6b2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9d6b2-112">Requirements</span></span>  
 <span data-ttu-id="9d6b2-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d6b2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d6b2-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d6b2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d6b2-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d6b2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d6b2-116">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d6b2-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6b2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9d6b2-117">See also</span></span>
- [<span data-ttu-id="9d6b2-118">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="9d6b2-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="9d6b2-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9d6b2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
