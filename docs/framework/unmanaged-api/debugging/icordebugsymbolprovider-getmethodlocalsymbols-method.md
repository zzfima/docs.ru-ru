---
title: Метод ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40123eff4028c1ebda898db27a5bd746571ba7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771402"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="9d640-102">Метод ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="9d640-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="9d640-103">Получает локальные символы метода с учетом относительного виртуального адреса (RVA) этого метода.</span><span class="sxs-lookup"><span data-stu-id="9d640-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d640-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d640-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d640-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d640-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="9d640-106">[in] Собственный относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="9d640-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="9d640-107">[in] Количество запрошенных локальных символов.</span><span class="sxs-lookup"><span data-stu-id="9d640-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="9d640-108">[out] Указатель на число  символов, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="9d640-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="9d640-109">[out] Указатель на [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) массив, содержащий локальные символы метода.</span><span class="sxs-lookup"><span data-stu-id="9d640-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d640-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d640-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d640-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="9d640-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d640-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9d640-112">Requirements</span></span>  
 <span data-ttu-id="9d640-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d640-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d640-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d640-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d640-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d640-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d640-116">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d640-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d640-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9d640-117">See also</span></span>

- [<span data-ttu-id="9d640-118">Метод GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="9d640-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="9d640-119">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="9d640-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="9d640-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9d640-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
