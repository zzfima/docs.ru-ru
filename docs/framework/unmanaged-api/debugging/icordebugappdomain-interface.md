---
title: Интерфейс ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12753ab65f9339e8f6c3049bb72755e87464eb1a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963112"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="dcd0b-102">Интерфейс ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="dcd0b-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="dcd0b-103">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="dcd0b-104">Этот интерфейс является подклассом ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dcd0b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dcd0b-105">Methods</span></span>  
  
|<span data-ttu-id="dcd0b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="dcd0b-106">Method</span></span>|<span data-ttu-id="dcd0b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dcd0b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dcd0b-108">Метод Attach</span><span class="sxs-lookup"><span data-stu-id="dcd0b-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="dcd0b-109">Присоединяет отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-110">Метод EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="dcd0b-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="dcd0b-111">Возвращает перечислитель для сборок в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-112">Метод EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="dcd0b-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="dcd0b-113">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-114">Метод EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="dcd0b-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="dcd0b-115">Возвращает перечислитель для всех активных шагов в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-116">Метод GetId</span><span class="sxs-lookup"><span data-stu-id="dcd0b-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="dcd0b-117">Возвращает уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-118">Метод GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="dcd0b-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="dcd0b-119">Возвращает объект ICorDebugModule с заданным интерфейсом метаданных.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="dcd0b-120">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="dcd0b-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="dcd0b-121">Возвращает имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-122">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="dcd0b-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="dcd0b-123">Возвращает указатель интерфейса на домен приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-124">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="dcd0b-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="dcd0b-125">Возвращает процесс, содержащий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="dcd0b-126">Метод IsAttached</span><span class="sxs-lookup"><span data-stu-id="dcd0b-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="dcd0b-127">Определяет, присоединен ли отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcd0b-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="dcd0b-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dcd0b-129">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="dcd0b-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcd0b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="dcd0b-130">Requirements</span></span>  
 <span data-ttu-id="dcd0b-131">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcd0b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcd0b-132">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="dcd0b-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcd0b-133">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="dcd0b-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcd0b-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcd0b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd0b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="dcd0b-135">See also</span></span>

- [<span data-ttu-id="dcd0b-136">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dcd0b-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
