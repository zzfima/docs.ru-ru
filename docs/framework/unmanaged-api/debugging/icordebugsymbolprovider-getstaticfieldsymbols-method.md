---
title: Метод ICorDebugSymbolProvider::GetStaticFieldSymbols
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18bfab7a666a4c715b2236f5101bcceacb5b2fed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072692"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="fb4b7-102">Метод ICorDebugSymbolProvider::GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="fb4b7-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="fb4b7-103">Получает символы статического поля, которые соответствуют сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="fb4b7-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb4b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb4b7-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb4b7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb4b7-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="fb4b7-106">[in] Число байтов в массиве `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="fb4b7-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="fb4b7-107">[in] Массив байтов, содержащий сигнатуру `typespec`.</span><span class="sxs-lookup"><span data-stu-id="fb4b7-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="fb4b7-108">[in] Количество запрошенных символов.</span><span class="sxs-lookup"><span data-stu-id="fb4b7-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="fb4b7-109">[out] Указатель на число  символов, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="fb4b7-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="fb4b7-110">[out] Указатель на [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) массив, содержащий запрошенные символы статического поля.</span><span class="sxs-lookup"><span data-stu-id="fb4b7-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb4b7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb4b7-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb4b7-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="fb4b7-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb4b7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fb4b7-113">Requirements</span></span>  
 <span data-ttu-id="fb4b7-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb4b7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb4b7-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb4b7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb4b7-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb4b7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb4b7-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb4b7-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb4b7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fb4b7-118">See also</span></span>

- [<span data-ttu-id="fb4b7-119">Метод GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="fb4b7-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="fb4b7-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="fb4b7-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="fb4b7-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fb4b7-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
