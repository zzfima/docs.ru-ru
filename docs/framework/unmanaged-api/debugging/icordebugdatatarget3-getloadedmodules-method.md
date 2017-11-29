---
title: "Метод ICorDebugDataTarget3::GetLoadedModules"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc4820d2c71830b297ed690c440c90cfff1f9601
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="c692e-102">Метод ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="c692e-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="c692e-103">Возвращает список модулей, загруженных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c692e-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c692e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c692e-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c692e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c692e-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="c692e-106">[in] Число модулей, для которых запрашиваются сведения.</span><span class="sxs-lookup"><span data-stu-id="c692e-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="c692e-107">[out] Указатель на число модулей, о которых возвращаются сведения.</span><span class="sxs-lookup"><span data-stu-id="c692e-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="c692e-108">[out] Указатель на массив [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) объектов, которые предоставляют сведения о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="c692e-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c692e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c692e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c692e-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c692e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c692e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c692e-111">Requirements</span></span>  
 <span data-ttu-id="c692e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c692e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c692e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c692e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c692e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c692e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c692e-115">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c692e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c692e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c692e-116">See Also</span></span>  
 [<span data-ttu-id="c692e-117">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="c692e-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="c692e-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c692e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
