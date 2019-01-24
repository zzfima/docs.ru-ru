---
title: Метод ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44771536ad7cb225c341505d4878d0cb4f2bdba5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568508"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="64acb-102">Метод ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="64acb-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="64acb-103">Получает локальные символы метода для указанного относительного виртуального адреса (RVA) этого метода.</span><span class="sxs-lookup"><span data-stu-id="64acb-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64acb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64acb-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64acb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64acb-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="64acb-106">[in] Собственный относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="64acb-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="64acb-107">[in] Количество запрошенных локальных символов.</span><span class="sxs-lookup"><span data-stu-id="64acb-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="64acb-108">[out] Указатель на число  символов, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="64acb-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="64acb-109">[out] Указатель на [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) массив, содержащий локальные символы метода.</span><span class="sxs-lookup"><span data-stu-id="64acb-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64acb-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="64acb-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64acb-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="64acb-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64acb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="64acb-112">Requirements</span></span>  
 <span data-ttu-id="64acb-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64acb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64acb-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64acb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64acb-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64acb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64acb-116">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64acb-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64acb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="64acb-117">See also</span></span>
- [<span data-ttu-id="64acb-118">Метод GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="64acb-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="64acb-119">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="64acb-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="64acb-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="64acb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
