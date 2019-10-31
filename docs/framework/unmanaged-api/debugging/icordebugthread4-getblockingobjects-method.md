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
ms.openlocfilehash: e4d5582b7a3df16db58ea0ed001dcbffcdcaab79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122453"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="db424-102">Метод ICorDebugThread4::GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="db424-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="db424-103">Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="db424-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db424-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db424-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="db424-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="db424-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="db424-106">заполняет Указатель на упорядоченное перечисление структур [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="db424-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db424-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="db424-107">Remarks</span></span>  
 <span data-ttu-id="db424-108">Первый элемент в возвращенном перечислении соответствует первой структуре, блокирующей поток.</span><span class="sxs-lookup"><span data-stu-id="db424-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="db424-109">Второй элемент соответствует блокирующему элементу, который обнаруживается при выполнении асинхронного вызова процедуры (APC) при блокировке в первом и т. д.</span><span class="sxs-lookup"><span data-stu-id="db424-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="db424-110">Перечисление допустимо только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="db424-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="db424-111">Этот метод должен вызываться, когда отлаживаемый объект находится в синхронизированном состоянии.</span><span class="sxs-lookup"><span data-stu-id="db424-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="db424-112">Если `ppBlockingObjectEnum` не является допустимым указателем, результат не определен.</span><span class="sxs-lookup"><span data-stu-id="db424-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="db424-113">Если поток заблокирован и ошибка не может быть определена, метод возвращает значение HRESULT, указывающее на ошибку; в противном случае возвращается значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="db424-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db424-114">Требования</span><span class="sxs-lookup"><span data-stu-id="db424-114">Requirements</span></span>  
 <span data-ttu-id="db424-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db424-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db424-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db424-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db424-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db424-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db424-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db424-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db424-119">См. также</span><span class="sxs-lookup"><span data-stu-id="db424-119">See also</span></span>

- [<span data-ttu-id="db424-120">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="db424-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="db424-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="db424-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="db424-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="db424-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
