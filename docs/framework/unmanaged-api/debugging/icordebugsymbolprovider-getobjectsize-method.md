---
title: "Метод ICorDebugSymbolProvider::GetObjectSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea9e0fcae9f98869884ad887a6c24de342512b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="8c833-102">Метод ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="8c833-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="8c833-103">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="8c833-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c833-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c833-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c833-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c833-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="8c833-106">[in] Число байтов в сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="8c833-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="8c833-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="8c833-107">typeSig</span></span>  
 <span data-ttu-id="8c833-108">[в] Сигнатура TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="8c833-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="8c833-109">[out] Указатель на размер объекта.</span><span class="sxs-lookup"><span data-stu-id="8c833-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c833-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c833-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c833-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8c833-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c833-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8c833-112">Requirements</span></span>  
 <span data-ttu-id="8c833-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c833-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c833-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c833-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c833-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c833-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c833-116">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c833-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c833-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8c833-117">See Also</span></span>  
 [<span data-ttu-id="8c833-118">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8c833-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="8c833-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c833-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
