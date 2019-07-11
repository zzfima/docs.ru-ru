---
title: Метод ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb7861e33a02b994c4c29569a811f4e2f3c44cec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762307"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="113e4-102">Метод ICorDebugMergedAssemblyRecord::GetVersion</span><span class="sxs-lookup"><span data-stu-id="113e4-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="113e4-103">Возвращает сведения о версии сборки.</span><span class="sxs-lookup"><span data-stu-id="113e4-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="113e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="113e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="113e4-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="113e4-106">[out] Указатель на основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="113e4-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="113e4-107">[out] Указатель на дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="113e4-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="113e4-108">[out] Указатель на номер сборки.</span><span class="sxs-lookup"><span data-stu-id="113e4-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="113e4-109">[out] Указатель на номер редакции.</span><span class="sxs-lookup"><span data-stu-id="113e4-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="113e4-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="113e4-110">Remarks</span></span>  
 <span data-ttu-id="113e4-111">Сведения о версии сборки см в разделе, посвященном классу <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="113e4-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="113e4-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="113e4-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="113e4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="113e4-113">Requirements</span></span>  
 <span data-ttu-id="113e4-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="113e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113e4-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="113e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="113e4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="113e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="113e4-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="113e4-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113e4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="113e4-118">See also</span></span>

- [<span data-ttu-id="113e4-119">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="113e4-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="113e4-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="113e4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
