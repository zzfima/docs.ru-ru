---
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72bad186bc8bb198a8c5b05fffcc0b2b6544482f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472425"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="5be23-102">Метод ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="5be23-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="5be23-103">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="5be23-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be23-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5be23-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5be23-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5be23-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="5be23-106">Объект [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) значение, представляющее адрес в модуле.</span><span class="sxs-lookup"><span data-stu-id="5be23-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="5be23-107">[out] Объект [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) значение, представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="5be23-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="5be23-108">Указатель на размер модуля.</span><span class="sxs-lookup"><span data-stu-id="5be23-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5be23-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5be23-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5be23-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="5be23-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5be23-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5be23-111">Requirements</span></span>  
 <span data-ttu-id="5be23-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5be23-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5be23-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5be23-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5be23-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5be23-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5be23-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5be23-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be23-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5be23-116">See also</span></span>
- [<span data-ttu-id="5be23-117">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="5be23-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="5be23-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5be23-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
