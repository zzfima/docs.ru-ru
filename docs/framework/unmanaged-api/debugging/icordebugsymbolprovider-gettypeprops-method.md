---
title: Метод ICorDebugSymbolProvider::GetTypeProps
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 435a814d20e039c794f4f9eeb024d5afbfcd6dbd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771198"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="b2ea8-102">Метод ICorDebugSymbolProvider::GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="b2ea8-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="b2ea8-103">Возвращает сведения о свойствах типа, такие как число сигнатур его универсальных параметров, для указанного относительного виртуального адреса (RVA) в таблице VTable.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ea8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2ea8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2ea8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2ea8-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="b2ea8-106">[in] Относительный виртуальный адрес (RVA) в VTable.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="b2ea8-107">[in] Размер массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="b2ea8-108">См. раздел примeчаний.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="b2ea8-109">[out] Указатель на размер возвращаемого массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="b2ea8-110">[out] Буфер, в котором хранятся сигнатуры TypeSpec для всех универсальных параметров.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2ea8-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2ea8-111">Remarks</span></span>  
 <span data-ttu-id="b2ea8-112">Чтобы получить требуемый размер типа `signature` массива, задайте `cbSignature` аргумент 0 и `signature` для **null**.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="b2ea8-113">После возврата метода параметр `pcbSignature` будет содержать число байт, требуемое для массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2ea8-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b2ea8-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2ea8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b2ea8-115">Requirements</span></span>  
 <span data-ttu-id="b2ea8-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2ea8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ea8-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2ea8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2ea8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2ea8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2ea8-119">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ea8-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ea8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b2ea8-120">See also</span></span>

- [<span data-ttu-id="b2ea8-121">Метод GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="b2ea8-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="b2ea8-122">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="b2ea8-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b2ea8-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b2ea8-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
