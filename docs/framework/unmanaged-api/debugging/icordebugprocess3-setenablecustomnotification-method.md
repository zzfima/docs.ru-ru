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
ms.openlocfilehash: 7501a8a0f8368049c87b3c90e1e707e12773a853
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531646"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="75d1c-102">Метод ICorDebugProcess3::SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="75d1c-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="75d1c-103">Включает и отключает пользовательскими уведомлениями отладчика указанного типа.</span><span class="sxs-lookup"><span data-stu-id="75d1c-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75d1c-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75d1c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75d1c-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="75d1c-106">[in] Тип, который задает пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="75d1c-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="75d1c-107">[in] `true` для включения пользовательскими уведомлениями отладчика; `false` отключение уведомлений.</span><span class="sxs-lookup"><span data-stu-id="75d1c-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="75d1c-108">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="75d1c-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75d1c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="75d1c-109">Remarks</span></span>  
 <span data-ttu-id="75d1c-110">Когда `fEnable` присваивается `true`, вызовы <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> триггера метод [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="75d1c-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="75d1c-111">Уведомления отключены по умолчанию. Таким образом отладчик необходимо указать все типы уведомлений, он знает о и может обработать.</span><span class="sxs-lookup"><span data-stu-id="75d1c-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="75d1c-112">Так как [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) действия класса доменом приложения, необходимо вызвать отладчик `SetEnableCustomNotification` для каждого домена приложений в процессе, если требуется получать уведомления из всего процесса.</span><span class="sxs-lookup"><span data-stu-id="75d1c-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="75d1c-113">Начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], только для поддерживаемых это уведомление зависимости между потоками.</span><span class="sxs-lookup"><span data-stu-id="75d1c-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75d1c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="75d1c-114">Requirements</span></span>  
 <span data-ttu-id="75d1c-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75d1c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75d1c-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75d1c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75d1c-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75d1c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75d1c-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75d1c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d1c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="75d1c-119">See also</span></span>
- [<span data-ttu-id="75d1c-120">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="75d1c-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="75d1c-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="75d1c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="75d1c-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="75d1c-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
