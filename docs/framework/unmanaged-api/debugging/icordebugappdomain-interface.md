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
ms.openlocfilehash: da7c0fb472df89d94fa702a13eff968a4c7e68e3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785032"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="7f31a-102">Интерфейс ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="7f31a-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="7f31a-103">Предоставляет методы для отладки доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="7f31a-104">Этот интерфейс является подклассом ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="7f31a-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f31a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7f31a-105">Methods</span></span>  
  
|<span data-ttu-id="7f31a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="7f31a-106">Method</span></span>|<span data-ttu-id="7f31a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7f31a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f31a-108">Метод Attach</span><span class="sxs-lookup"><span data-stu-id="7f31a-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="7f31a-109">Присоединяет отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="7f31a-110">Метод EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="7f31a-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="7f31a-111">Возвращает перечислитель для сборок в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="7f31a-112">Метод EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="7f31a-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="7f31a-113">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="7f31a-114">Метод EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="7f31a-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="7f31a-115">Возвращает перечислитель для всех активных шагов в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="7f31a-116">Метод GetId</span><span class="sxs-lookup"><span data-stu-id="7f31a-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="7f31a-117">Возвращает уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="7f31a-118">Метод GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="7f31a-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="7f31a-119">Возвращает объект ICorDebugModule с заданным интерфейсом метаданных.</span><span class="sxs-lookup"><span data-stu-id="7f31a-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="7f31a-120">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="7f31a-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="7f31a-121">Возвращает имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="7f31a-122">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="7f31a-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="7f31a-123">Возвращает указатель интерфейса на домен приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7f31a-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="7f31a-124">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="7f31a-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="7f31a-125">Возвращает процесс, содержащий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="7f31a-126">Метод IsAttached</span><span class="sxs-lookup"><span data-stu-id="7f31a-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="7f31a-127">Определяет, присоединен ли отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="7f31a-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f31a-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="7f31a-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f31a-129">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7f31a-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f31a-130">Требования</span><span class="sxs-lookup"><span data-stu-id="7f31a-130">Requirements</span></span>  
 <span data-ttu-id="7f31a-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f31a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f31a-132">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f31a-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f31a-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f31a-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f31a-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f31a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f31a-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f31a-135">See also</span></span>

- [<span data-ttu-id="7f31a-136">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7f31a-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
