---
title: "Метод ICorDebugThread4::GetBlockingObjects"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.GetBlockingObjects Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6783d7f9af67acdff147cc46ea4f856f9b10bf3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="943c7-102">Метод ICorDebugThread4::GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="943c7-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="943c7-103">Предоставляет перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры, обеспечивающие поток сведений о блокировании.</span><span class="sxs-lookup"><span data-stu-id="943c7-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="943c7-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a><span data-ttu-id="943c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="943c7-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="943c7-106">[out] Указатель на перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="943c7-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="943c7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="943c7-107">Remarks</span></span>  
 <span data-ttu-id="943c7-108">Первый элемент возвращенного перечисления соответствует первой структуре, блокирующей поток.</span><span class="sxs-lookup"><span data-stu-id="943c7-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="943c7-109">Второй элемент соответствует элементу блокировки, возникшей во время выполнения асинхронный вызов процедур (APC) при блокировке на первом и т. д.</span><span class="sxs-lookup"><span data-stu-id="943c7-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="943c7-110">Перечисление является допустимым только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="943c7-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="943c7-111">Этот метод должен вызываться при нахождении отладчика в синхронизированном состоянии.</span><span class="sxs-lookup"><span data-stu-id="943c7-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="943c7-112">Если `ppBlockingObjectEnum` не является допустимым указателем, результат будет неопределенным.</span><span class="sxs-lookup"><span data-stu-id="943c7-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="943c7-113">Если ошибку не удается определить поток заблокирован, метод возвращает значение HRESULT, указывающее на сбой; в противном случае возвращается значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="943c7-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943c7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="943c7-114">Requirements</span></span>  
 <span data-ttu-id="943c7-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943c7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943c7-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="943c7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="943c7-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="943c7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="943c7-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="943c7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943c7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="943c7-119">See Also</span></span>  
 [<span data-ttu-id="943c7-120">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="943c7-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="943c7-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="943c7-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="943c7-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="943c7-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
