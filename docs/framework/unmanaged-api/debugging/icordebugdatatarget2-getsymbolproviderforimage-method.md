---
title: Метод ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e148adf3f9b00715d86d2e6f4a40430f099c935d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469265"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="931e4-102">Метод ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="931e4-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="931e4-103">Возвращает поставщика символов для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="931e4-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="931e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="931e4-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="931e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="931e4-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="931e4-106">[in] Объект [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) значение, представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="931e4-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="931e4-107">[out] Указатель на адрес [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="931e4-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="931e4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="931e4-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="931e4-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="931e4-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="931e4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="931e4-110">Requirements</span></span>  
 <span data-ttu-id="931e4-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="931e4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="931e4-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="931e4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="931e4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="931e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="931e4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="931e4-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931e4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="931e4-115">See also</span></span>
- [<span data-ttu-id="931e4-116">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="931e4-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="931e4-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="931e4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
