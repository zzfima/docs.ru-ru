---
title: Метод ICorDebugThread4::GetBlockingObjects
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55251a3adfa67c1dac3b6952a37217e3eeb4c04a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="cf54a-102">Метод ICorDebugThread4::GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="cf54a-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="cf54a-103">Предоставляет перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры, обеспечивающие поток сведений о блокировании.</span><span class="sxs-lookup"><span data-stu-id="cf54a-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf54a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf54a-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf54a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf54a-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="cf54a-106">[out] Указатель на перечисление упорядоченный [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="cf54a-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf54a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf54a-107">Remarks</span></span>  
 <span data-ttu-id="cf54a-108">Первый элемент возвращенного перечисления соответствует первой структуре, блокирующей поток.</span><span class="sxs-lookup"><span data-stu-id="cf54a-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="cf54a-109">Второй элемент соответствует элементу блокировки, возникшей во время выполнения асинхронный вызов процедур (APC) при блокировке на первом и т. д.</span><span class="sxs-lookup"><span data-stu-id="cf54a-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="cf54a-110">Перечисление является допустимым только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="cf54a-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="cf54a-111">Этот метод должен вызываться при нахождении отладчика в синхронизированном состоянии.</span><span class="sxs-lookup"><span data-stu-id="cf54a-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="cf54a-112">Если `ppBlockingObjectEnum` не является допустимым указателем, результат будет неопределенным.</span><span class="sxs-lookup"><span data-stu-id="cf54a-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="cf54a-113">Если ошибку не удается определить поток заблокирован, метод возвращает значение HRESULT, указывающее на сбой; в противном случае возвращается значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="cf54a-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf54a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cf54a-114">Requirements</span></span>  
 <span data-ttu-id="cf54a-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf54a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf54a-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf54a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf54a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf54a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf54a-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf54a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf54a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cf54a-119">See Also</span></span>  
 [<span data-ttu-id="cf54a-120">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="cf54a-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="cf54a-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cf54a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cf54a-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="cf54a-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
