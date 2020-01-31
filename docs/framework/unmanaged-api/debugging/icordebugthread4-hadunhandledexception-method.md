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
ms.openlocfilehash: f558a4c94afeb69f58605958ddcb91e4be772c39
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791351"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="6cc6b-102">Метод ICorDebugThread4::HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="6cc6b-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="6cc6b-103">Указывает, имел ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cc6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cc6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cc6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6cc6b-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="6cc6b-106">заполняет Указатель на адрес упорядоченного перечисления структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="6cc6b-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cc6b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6cc6b-107">Return Value</span></span>  
 <span data-ttu-id="6cc6b-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6cc6b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6cc6b-109">HRESULT</span></span>|<span data-ttu-id="6cc6b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6cc6b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6cc6b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6cc6b-111">S_OK</span></span>|<span data-ttu-id="6cc6b-112">В потоке возникло необработанное исключение с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="6cc6b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6cc6b-113">S_FALSE</span></span>|<span data-ttu-id="6cc6b-114">В потоке никогда не было необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cc6b-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="6cc6b-115">Remarks</span></span>  
 <span data-ttu-id="6cc6b-116">Этот метод указывает, имел ли у потока когда-либо необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="6cc6b-117">К моменту запуска обратного вызова необработанного исключения или инициализации собственного JIT-присоединения этот метод гарантированно возвращает S_OK.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="6cc6b-118">Нет никакой гарантии, что метод [ICorDebugThread. жеткуррентексцептион](icordebugthread-getcurrentexception-method.md) будет возвращать необработанное исключение; Тем не менее, если процесс еще не был продолжен после получения обратного вызова необработанного исключения или собственного JIT-присоединения.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="6cc6b-119">Кроме того, во время выполнения собственного JIT-присоединения можно (хотя маловероятно) иметь более одного потока с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="6cc6b-120">В этом случае нет способа определить, какое исключение активировало JIT-присоединение.</span><span class="sxs-lookup"><span data-stu-id="6cc6b-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cc6b-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6cc6b-121">Requirements</span></span>  
 <span data-ttu-id="6cc6b-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cc6b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cc6b-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cc6b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cc6b-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cc6b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cc6b-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cc6b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cc6b-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="6cc6b-126">See also</span></span>

- [<span data-ttu-id="6cc6b-127">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="6cc6b-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="6cc6b-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6cc6b-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6cc6b-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="6cc6b-129">Debugging</span></span>](index.md)
