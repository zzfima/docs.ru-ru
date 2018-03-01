---
title: "Метод ICorDebugManagedCallback3::CustomNotification"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c42443b0d1e355d4233909357c341763298160e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="55038-102">Метод ICorDebugManagedCallback3::CustomNotification</span><span class="sxs-lookup"><span data-stu-id="55038-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="55038-103">Указывает, что создано пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="55038-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55038-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55038-104">Syntax</span></span>  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55038-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55038-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="55038-106">[in] Указатель на поток, вызвавший уведомление.</span><span class="sxs-lookup"><span data-stu-id="55038-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="55038-107">[in] Указатель на домен приложения, который содержит поток, вызвавший уведомление.</span><span class="sxs-lookup"><span data-stu-id="55038-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55038-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="55038-108">Return Value</span></span>  
 <span data-ttu-id="55038-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="55038-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="55038-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55038-110">HRESULT</span></span>|<span data-ttu-id="55038-111">Описание</span><span class="sxs-lookup"><span data-stu-id="55038-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55038-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="55038-112">S_OK</span></span>|<span data-ttu-id="55038-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="55038-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="55038-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="55038-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55038-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="55038-115">Remarks</span></span>  
 <span data-ttu-id="55038-116">В последующем вызове [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) метод извлекает объект потока, который был передан в <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="55038-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="55038-117">Тип объекта потока должна быть ранее включена, вызвав [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="55038-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="55038-118">Отладчик может считывать параметры конкретного типа из поля объекта потока и сохранять ответы в поля.</span><span class="sxs-lookup"><span data-stu-id="55038-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="55038-119">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейса не применяет никакой политики типы уведомлений или их содержимому, а семантика уведомлений определяется исключительно контрактом между отладчики, приложения и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="55038-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55038-120">Требования</span><span class="sxs-lookup"><span data-stu-id="55038-120">Requirements</span></span>  
 <span data-ttu-id="55038-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55038-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55038-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55038-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55038-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55038-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55038-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55038-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55038-125">См. также</span><span class="sxs-lookup"><span data-stu-id="55038-125">See Also</span></span>  
 [<span data-ttu-id="55038-126">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="55038-126">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [<span data-ttu-id="55038-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="55038-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="55038-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="55038-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
