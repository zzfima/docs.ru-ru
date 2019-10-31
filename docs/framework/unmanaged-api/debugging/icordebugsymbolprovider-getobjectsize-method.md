---
title: 'Метод метод icordebugsymbolprovider:: Жетобжектсизе'
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: a5c0fe6d73302abbfabe2272cc878d6fd8f5fdec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138821"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="b7d40-102">Метод метод icordebugsymbolprovider:: Жетобжектсизе</span><span class="sxs-lookup"><span data-stu-id="b7d40-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="b7d40-103">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="b7d40-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7d40-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7d40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7d40-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="b7d40-106">[in] Число байтов в сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="b7d40-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="b7d40-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="b7d40-107">typeSig</span></span>  
 <span data-ttu-id="b7d40-108">[в] Сигнатура TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="b7d40-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="b7d40-109">[out] Указатель на размер объекта.</span><span class="sxs-lookup"><span data-stu-id="b7d40-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7d40-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="b7d40-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7d40-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b7d40-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d40-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b7d40-112">Requirements</span></span>  
 <span data-ttu-id="b7d40-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d40-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d40-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7d40-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7d40-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7d40-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7d40-116">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d40-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d40-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b7d40-117">See also</span></span>

- [<span data-ttu-id="b7d40-118">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="b7d40-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b7d40-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b7d40-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
