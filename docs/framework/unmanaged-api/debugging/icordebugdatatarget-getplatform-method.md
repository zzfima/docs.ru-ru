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
ms.openlocfilehash: 1065c8d710ddbd6088ee0db694a43e098564e707
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750379"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="2f6a3-102">Метод ICorDebugDataTarget::GetPlatform</span><span class="sxs-lookup"><span data-stu-id="2f6a3-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="2f6a3-103">Сведения о платформе, включая архитектуру процессора и операционной системы, на котором выполняется целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f6a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f6a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f6a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f6a3-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="2f6a3-106">[out] Указатель на [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) перечисление, описывающее целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f6a3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f6a3-107">Remarks</span></span>  
 <span data-ttu-id="2f6a3-108">`CorDebugPlatformEnum` Возвращаемое значение перечисления используется [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс, чтобы определить сведения о целевом процессе, такие как его размер указателя, структуры адресного пространства, набор регистров, формат команд, структура контекста и соглашения о вызовах.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="2f6a3-109">`pTargetPlatform` Может указывать на платформу, эмулируется для целевого объекта вместо указания фактическое оборудование используется.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="2f6a3-110">Например, следует использовать процесс, который работает в Windows в среде Windows (WOW) в 64-разрядной версии операционной системы Windows `CORDB_PLATFORM_WINDOWS_X86` значение [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="2f6a3-111">Этот метод должен завершиться успешно.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-111">This method must succeed.</span></span> <span data-ttu-id="2f6a3-112">Если происходит сбой, целевая платформа — непригодным для использования.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="2f6a3-113">Метод может завершиться ошибкой по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="2f6a3-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="2f6a3-114">Платформа, которая является эмулируемая для целевого объекта не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="2f6a3-115">Фактическое оборудование на целевой платформе непригодным для использования.</span><span class="sxs-lookup"><span data-stu-id="2f6a3-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f6a3-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2f6a3-116">Requirements</span></span>  
 <span data-ttu-id="2f6a3-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f6a3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f6a3-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f6a3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f6a3-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f6a3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f6a3-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f6a3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6a3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2f6a3-121">See also</span></span>

- [<span data-ttu-id="2f6a3-122">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="2f6a3-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="2f6a3-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2f6a3-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2f6a3-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="2f6a3-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
