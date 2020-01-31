---
title: Метод ICorDebugManagedCallback3::CustomNotification
ms.date: 03/30/2017
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
ms.openlocfilehash: 078f90387a475559067d402610ec264f4076ae01
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793254"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="666f0-102">Метод ICorDebugManagedCallback3::CustomNotification</span><span class="sxs-lookup"><span data-stu-id="666f0-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="666f0-103">Указывает, что было создано пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="666f0-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="666f0-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="666f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="666f0-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="666f0-106">окне Указатель на поток, создавший уведомление.</span><span class="sxs-lookup"><span data-stu-id="666f0-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="666f0-107">окне Указатель на домен приложения, содержащий поток, вызвавший уведомление.</span><span class="sxs-lookup"><span data-stu-id="666f0-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="666f0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="666f0-108">Return Value</span></span>  
 <span data-ttu-id="666f0-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="666f0-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="666f0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="666f0-110">HRESULT</span></span>|<span data-ttu-id="666f0-111">Описание</span><span class="sxs-lookup"><span data-stu-id="666f0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="666f0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="666f0-112">S_OK</span></span>|<span data-ttu-id="666f0-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="666f0-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="666f0-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="666f0-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="666f0-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="666f0-115">Remarks</span></span>  
 <span data-ttu-id="666f0-116">Последующий вызов метода [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) извлекает объект потока, который был передан методу <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="666f0-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="666f0-117">Тип объекта потока должен быть ранее включен путем вызова метода [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="666f0-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="666f0-118">Отладчик может считывать параметры конкретного типа из полей объекта потока и может сохранять ответы в полях.</span><span class="sxs-lookup"><span data-stu-id="666f0-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="666f0-119">Интерфейс [ICorDebug](icordebug-interface.md) не накладывает политики на типы уведомлений или их содержимое, а семантика уведомлений является строго контрактом между отладчиками, приложениями и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="666f0-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="666f0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="666f0-120">Requirements</span></span>  
 <span data-ttu-id="666f0-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="666f0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="666f0-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="666f0-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="666f0-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="666f0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="666f0-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="666f0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666f0-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="666f0-125">See also</span></span>

- [<span data-ttu-id="666f0-126">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="666f0-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="666f0-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="666f0-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="666f0-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="666f0-128">Debugging</span></span>](index.md)
