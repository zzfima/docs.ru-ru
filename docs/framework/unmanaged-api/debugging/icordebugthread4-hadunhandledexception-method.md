---
title: Метод ICorDebugThread4::HadUnhandledException
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ef4049ee8b1a4881128047b4d7e50fd0a28ea31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499203"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="fd721-102">Метод ICorDebugThread4::HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="fd721-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="fd721-103">Указывает, возникало ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="fd721-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd721-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd721-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd721-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd721-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="fd721-106">[out] Указатель на адрес, упорядоченный перечисления [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="fd721-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd721-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd721-107">Return Value</span></span>  
 <span data-ttu-id="fd721-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="fd721-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fd721-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd721-109">HRESULT</span></span>|<span data-ttu-id="fd721-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fd721-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd721-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd721-111">S_OK</span></span>|<span data-ttu-id="fd721-112">Поток был необработанное исключение с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="fd721-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="fd721-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fd721-113">S_FALSE</span></span>|<span data-ttu-id="fd721-114">Поток никогда не устанавливался необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="fd721-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd721-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd721-115">Remarks</span></span>  
 <span data-ttu-id="fd721-116">Этот метод указывает, возникало ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="fd721-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="fd721-117">К моменту запущен обратный вызов необработанного исключения или собственного JIT-присоединением инициируется, этот метод гарантированно возвращает S_OK.</span><span class="sxs-lookup"><span data-stu-id="fd721-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="fd721-118">Нет никакой гарантии, [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) метод возвращает необработанное исключение; тем не менее, он будет, если процесс не еще продолжается после получения обратного вызова необработанного исключения или при собственного JIT-присоединения.</span><span class="sxs-lookup"><span data-stu-id="fd721-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="fd721-119">Кроме того можно (хотя и маловероятно) иметь более одного потока с необработанное исключение во время активации собственного JIT-присоединением.</span><span class="sxs-lookup"><span data-stu-id="fd721-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="fd721-120">В этом случае нет способа определить, какое исключение инициировало JIT-присоединением.</span><span class="sxs-lookup"><span data-stu-id="fd721-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd721-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fd721-121">Requirements</span></span>  
 <span data-ttu-id="fd721-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd721-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd721-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd721-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd721-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd721-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd721-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd721-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd721-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fd721-126">See also</span></span>
- [<span data-ttu-id="fd721-127">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="fd721-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="fd721-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fd721-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fd721-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="fd721-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
