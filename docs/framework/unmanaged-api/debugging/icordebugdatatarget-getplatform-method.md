---
title: Метод ICorDebugDataTarget::GetPlatform
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17ae761b2d48552aded8191ddbea26552d8da277
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411022"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="8c89d-102">Метод ICorDebugDataTarget::GetPlatform</span><span class="sxs-lookup"><span data-stu-id="8c89d-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="8c89d-103">Предоставляет сведения о платформе, включая архитектуру процессора и операционной системы, на котором выполняется целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="8c89d-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c89d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c89d-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c89d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c89d-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="8c89d-106">[out] Указатель на [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) перечисление, описывающее целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="8c89d-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c89d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c89d-107">Remarks</span></span>  
 <span data-ttu-id="8c89d-108">`CorDebugPlatformEnum` Возвращаемое значение перечисления используется [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс для определения сведений целевого процесса, такие как его размер указателя, структура адресного пространства, набор регистров, формат команд, структура контекста и соглашения о вызовах.</span><span class="sxs-lookup"><span data-stu-id="8c89d-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="8c89d-109">`pTargetPlatform` Может указывать на платформу, эмулируется для целевого объекта вместо указания фактическое оборудование используется.</span><span class="sxs-lookup"><span data-stu-id="8c89d-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="8c89d-110">Например, следует использовать процесс, который выполняется в Windows в среде Windows (WOW) в 64-разрядной версии операционной системы Windows `CORDB_PLATFORM_WINDOWS_X86` значение [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="8c89d-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="8c89d-111">Этот метод должен завершиться успешно.</span><span class="sxs-lookup"><span data-stu-id="8c89d-111">This method must succeed.</span></span> <span data-ttu-id="8c89d-112">В случае неудачи целевая платформа не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="8c89d-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="8c89d-113">Метод может завершиться ошибкой по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="8c89d-113">The method may fail for the following reasons:</span></span>  
  
-   <span data-ttu-id="8c89d-114">Платформы, которая эмулируется для целевого объекта не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="8c89d-114">The platform that is being emulated for the target is unusable.</span></span>  
  
-   <span data-ttu-id="8c89d-115">Фактические аппаратные средства целевой платформы не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="8c89d-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c89d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="8c89d-116">Requirements</span></span>  
 <span data-ttu-id="8c89d-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c89d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c89d-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c89d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c89d-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c89d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c89d-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c89d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c89d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8c89d-121">See Also</span></span>  
 [<span data-ttu-id="8c89d-122">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="8c89d-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="8c89d-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c89d-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8c89d-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="8c89d-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
