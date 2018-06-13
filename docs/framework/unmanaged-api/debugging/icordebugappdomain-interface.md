---
title: ICorDebugAppDomain интерфейс1
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
ms.openlocfilehash: 84a11b6264ac0e241c1975eea5626edbdddce206
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406881"
---
# <a name="icordebugappdomain-interface1"></a><span data-ttu-id="2f662-102">ICorDebugAppDomain интерфейс1</span><span class="sxs-lookup"><span data-stu-id="2f662-102">ICorDebugAppDomain Interface1</span></span>
<span data-ttu-id="2f662-103">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="2f662-104">Этот интерфейс является подклассом ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="2f662-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f662-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2f662-105">Methods</span></span>  
  
|<span data-ttu-id="2f662-106">Метод</span><span class="sxs-lookup"><span data-stu-id="2f662-106">Method</span></span>|<span data-ttu-id="2f662-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2f662-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f662-108">Метод Attach</span><span class="sxs-lookup"><span data-stu-id="2f662-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="2f662-109">Присоединяет отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="2f662-110">Метод EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="2f662-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="2f662-111">Получает перечислитель для сборок в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="2f662-112">Метод EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="2f662-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="2f662-113">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="2f662-114">Метод EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="2f662-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="2f662-115">Возвращает перечислитель для всех активных средств организации пошагового режима в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="2f662-116">Метод GetId</span><span class="sxs-lookup"><span data-stu-id="2f662-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="2f662-117">Получает уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="2f662-118">Метод GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="2f662-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="2f662-119">Возвращает объект ICorDebugModule с интерфейсом указанных метаданных.</span><span class="sxs-lookup"><span data-stu-id="2f662-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="2f662-120">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="2f662-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="2f662-121">Возвращает имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="2f662-122">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="2f662-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="2f662-123">Получает указатель интерфейса на домен приложения среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="2f662-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="2f662-124">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="2f662-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="2f662-125">Получает процесс, содержащий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="2f662-126">Метод IsAttached</span><span class="sxs-lookup"><span data-stu-id="2f662-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="2f662-127">Определяет, присоединен ли отладчик в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="2f662-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f662-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f662-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f662-129">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="2f662-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f662-130">Требования</span><span class="sxs-lookup"><span data-stu-id="2f662-130">Requirements</span></span>  
 <span data-ttu-id="2f662-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f662-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f662-132">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f662-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f662-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f662-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f662-134">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f662-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f662-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2f662-135">See Also</span></span>  
 [<span data-ttu-id="2f662-136">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2f662-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
