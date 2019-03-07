---
title: Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a979fd3dd8fc8fc4266f7bd69be0e71b8a400a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477683"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="4afb5-102">Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="4afb5-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="4afb5-103">Возвращает символьные записи для всех объединенных сборок.</span><span class="sxs-lookup"><span data-stu-id="4afb5-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4afb5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4afb5-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4afb5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4afb5-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="4afb5-106">[in] Количество запрошенных символьных записей.</span><span class="sxs-lookup"><span data-stu-id="4afb5-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="4afb5-107">[out] Указатель на число  символьных записей, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="4afb5-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="4afb5-108">Указатель на массив [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="4afb5-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4afb5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4afb5-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4afb5-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="4afb5-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4afb5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4afb5-111">Requirements</span></span>  
 <span data-ttu-id="4afb5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4afb5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4afb5-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4afb5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4afb5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4afb5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4afb5-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4afb5-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afb5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4afb5-116">See also</span></span>
- [<span data-ttu-id="4afb5-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4afb5-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4afb5-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4afb5-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
