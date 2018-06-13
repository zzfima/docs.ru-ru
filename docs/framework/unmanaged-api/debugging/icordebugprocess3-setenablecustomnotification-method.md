---
title: Метод ICorDebugProcess3::SetEnableCustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a84061cff7cc5dbdeba1e0e66396e04a8f345cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423160"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="30d43-102">Метод ICorDebugProcess3::SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="30d43-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="30d43-103">Включает и отключает пользовательскими уведомлениями отладчика заданного типа.</span><span class="sxs-lookup"><span data-stu-id="30d43-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30d43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30d43-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30d43-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30d43-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="30d43-106">[in] Тип, определяющий пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="30d43-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="30d43-107">[in] `true` Включение пользовательскими уведомлениями отладчика; `false` отключения уведомлений.</span><span class="sxs-lookup"><span data-stu-id="30d43-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="30d43-108">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="30d43-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30d43-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="30d43-109">Remarks</span></span>  
 <span data-ttu-id="30d43-110">Когда `fEnable` задано значение `true`, вызовы <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> триггер метод [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="30d43-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="30d43-111">Уведомления отключены по умолчанию. Таким образом отладчик необходимо указать все типы уведомлений, он знает об и требуется обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="30d43-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="30d43-112">Поскольку [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) действия класса доменом приложения, отладчик должен вызвать `SetEnableCustomNotification` для каждого домена приложений в процессе, если требуется получать уведомления из всего процесса.</span><span class="sxs-lookup"><span data-stu-id="30d43-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="30d43-113">Начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], единственным поддерживаемым уведомлением является уведомление зависимости между потоками.</span><span class="sxs-lookup"><span data-stu-id="30d43-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30d43-114">Требования</span><span class="sxs-lookup"><span data-stu-id="30d43-114">Requirements</span></span>  
 <span data-ttu-id="30d43-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30d43-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30d43-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30d43-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30d43-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30d43-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30d43-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30d43-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d43-119">См. также</span><span class="sxs-lookup"><span data-stu-id="30d43-119">See Also</span></span>  
 [<span data-ttu-id="30d43-120">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="30d43-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [<span data-ttu-id="30d43-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="30d43-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="30d43-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="30d43-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
