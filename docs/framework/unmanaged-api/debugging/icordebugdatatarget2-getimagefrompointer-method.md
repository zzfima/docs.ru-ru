---
title: "Метод ICorDebugDataTarget2::GetImageFromPointer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e56f65aea12c71145c99a9a195b910ef2876aa09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="4b3a7-102">Метод ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="4b3a7-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="4b3a7-103">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="4b3a7-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b3a7-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b3a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b3a7-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="4b3a7-106">Объект [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) значение, представляющее адрес в модуле.</span><span class="sxs-lookup"><span data-stu-id="4b3a7-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="4b3a7-107">[out] Объект [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) значение, представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="4b3a7-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="4b3a7-108">Указатель на размер модуля.</span><span class="sxs-lookup"><span data-stu-id="4b3a7-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b3a7-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b3a7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b3a7-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="4b3a7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b3a7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4b3a7-111">Requirements</span></span>  
 <span data-ttu-id="4b3a7-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b3a7-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b3a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b3a7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b3a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b3a7-115">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3a7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3a7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4b3a7-116">See Also</span></span>  
 [<span data-ttu-id="4b3a7-117">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="4b3a7-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="4b3a7-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4b3a7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
