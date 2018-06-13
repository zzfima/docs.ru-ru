---
title: ICorDebugAppDomainEnum интерфейс1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddf8db3b02ba4766d046fc549eec8add31f51069
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407924"
---
# <a name="icordebugappdomainenum-interface1"></a><span data-ttu-id="95c52-102">ICorDebugAppDomainEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="95c52-102">ICorDebugAppDomainEnum Interface1</span></span>
<span data-ttu-id="95c52-103">Предоставляет `Next` метод, возвращающий заданное число `ICorDebugAppDomainEnum` значений, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="95c52-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="95c52-104">Этот интерфейс является подклассом «ICorDebugEnum».</span><span class="sxs-lookup"><span data-stu-id="95c52-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95c52-105">Методы</span><span class="sxs-lookup"><span data-stu-id="95c52-105">Methods</span></span>  
  
|<span data-ttu-id="95c52-106">Метод</span><span class="sxs-lookup"><span data-stu-id="95c52-106">Method</span></span>|<span data-ttu-id="95c52-107">Описание</span><span class="sxs-lookup"><span data-stu-id="95c52-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95c52-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="95c52-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="95c52-109">Возвращает заданное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="95c52-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95c52-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="95c52-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95c52-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="95c52-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c52-112">Требования</span><span class="sxs-lookup"><span data-stu-id="95c52-112">Requirements</span></span>  
 <span data-ttu-id="95c52-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95c52-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c52-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95c52-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95c52-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95c52-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95c52-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c52-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c52-117">См. также</span><span class="sxs-lookup"><span data-stu-id="95c52-117">See Also</span></span>  
 [<span data-ttu-id="95c52-118">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="95c52-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="95c52-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="95c52-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
