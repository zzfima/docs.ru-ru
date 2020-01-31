---
title: Метод ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: fce7410b5ae9571af0c8a5963596e2af41737798
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791568"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="73891-102">Метод ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="73891-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="73891-103">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="73891-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73891-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73891-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73891-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73891-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="73891-106">[in] Число байтов в сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="73891-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="73891-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="73891-107">typeSig</span></span>  
 <span data-ttu-id="73891-108">[в] Сигнатура TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="73891-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="73891-109">[out] Указатель на размер объекта.</span><span class="sxs-lookup"><span data-stu-id="73891-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73891-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="73891-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73891-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="73891-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73891-112">Требования</span><span class="sxs-lookup"><span data-stu-id="73891-112">Requirements</span></span>  
 <span data-ttu-id="73891-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73891-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73891-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73891-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73891-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73891-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73891-116">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73891-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73891-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="73891-117">See also</span></span>

- [<span data-ttu-id="73891-118">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="73891-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="73891-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="73891-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
