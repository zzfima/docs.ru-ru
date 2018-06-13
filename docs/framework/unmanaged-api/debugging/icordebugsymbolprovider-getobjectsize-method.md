---
title: Метод ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1da526ac133604fa43081f86988459c4238517c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421507"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="8c35b-102">Метод ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="8c35b-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="8c35b-103">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="8c35b-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c35b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c35b-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c35b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c35b-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="8c35b-106">[in] Число байтов в сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="8c35b-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="8c35b-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="8c35b-107">typeSig</span></span>  
 <span data-ttu-id="8c35b-108">[в] Сигнатура TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="8c35b-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="8c35b-109">[out] Указатель на размер объекта.</span><span class="sxs-lookup"><span data-stu-id="8c35b-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c35b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c35b-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c35b-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8c35b-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c35b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8c35b-112">Requirements</span></span>  
 <span data-ttu-id="8c35b-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c35b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c35b-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c35b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c35b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c35b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c35b-116">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c35b-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c35b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8c35b-117">See Also</span></span>  
 [<span data-ttu-id="8c35b-118">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8c35b-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="8c35b-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c35b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
