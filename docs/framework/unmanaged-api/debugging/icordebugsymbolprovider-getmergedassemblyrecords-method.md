---
title: Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f7859b095d80edb5592af1386457ad72b85bc48
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957385"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="2767d-102">Метод ICorDebugSymbolProvider::GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="2767d-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="2767d-103">Возвращает символьные записи для всех объединенных сборок.</span><span class="sxs-lookup"><span data-stu-id="2767d-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2767d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2767d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2767d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2767d-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="2767d-106">[in] Количество запрошенных символьных записей.</span><span class="sxs-lookup"><span data-stu-id="2767d-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="2767d-107">[out] Указатель на число  символьных записей, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="2767d-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="2767d-108">Указатель на массив объектов [икордебугмержедассемблирекорд](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2767d-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2767d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2767d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2767d-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="2767d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2767d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2767d-111">Requirements</span></span>  
 <span data-ttu-id="2767d-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2767d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2767d-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2767d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2767d-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="2767d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2767d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2767d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2767d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2767d-116">See also</span></span>

- [<span data-ttu-id="2767d-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="2767d-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="2767d-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2767d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
