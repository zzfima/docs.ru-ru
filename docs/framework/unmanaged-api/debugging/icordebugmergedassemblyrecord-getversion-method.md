---
title: "Метод ICorDebugMergedAssemblyRecord::GetVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6a3865a82efec63aa85f4a0eee286bf8b79bd00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="188e2-102">Метод ICorDebugMergedAssemblyRecord::GetVersion</span><span class="sxs-lookup"><span data-stu-id="188e2-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="188e2-103">Возвращает сведения о версии сборки.</span><span class="sxs-lookup"><span data-stu-id="188e2-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="188e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="188e2-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="188e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="188e2-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="188e2-106">[out] Указатель на основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="188e2-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="188e2-107">[out] Указатель на дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="188e2-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="188e2-108">[out] Указатель на номер сборки.</span><span class="sxs-lookup"><span data-stu-id="188e2-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="188e2-109">[out] Указатель на номер редакции.</span><span class="sxs-lookup"><span data-stu-id="188e2-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="188e2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="188e2-110">Remarks</span></span>  
 <span data-ttu-id="188e2-111">Сведения о версии сборки см в разделе, посвященном классу <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="188e2-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="188e2-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="188e2-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="188e2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="188e2-113">Requirements</span></span>  
 <span data-ttu-id="188e2-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="188e2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="188e2-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="188e2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="188e2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="188e2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="188e2-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="188e2-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188e2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="188e2-118">See Also</span></span>  
 [<span data-ttu-id="188e2-119">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="188e2-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="188e2-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="188e2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
