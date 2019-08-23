---
title: Метод ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e5a6e70d5148756a5ed8d17c56577da920d1b69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911452"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="a3cb2-102">Метод ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="a3cb2-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="a3cb2-103">Возвращает поставщика символов для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="a3cb2-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3cb2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3cb2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3cb2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a3cb2-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="a3cb2-106">окне Значение [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="a3cb2-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="a3cb2-107">заполняет Указатель на адрес объекта [метод icordebugsymbolprovider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a3cb2-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3cb2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a3cb2-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3cb2-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a3cb2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3cb2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a3cb2-110">Requirements</span></span>  
 <span data-ttu-id="a3cb2-111">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3cb2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3cb2-112">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a3cb2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3cb2-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="a3cb2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3cb2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3cb2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cb2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a3cb2-115">See also</span></span>

- [<span data-ttu-id="a3cb2-116">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="a3cb2-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a3cb2-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a3cb2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
