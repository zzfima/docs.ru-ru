---
title: Интерфейс ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4e245e96ac9d47db10072e50a5b3c516d5dd27
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962681"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="2aabc-102">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="2aabc-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="2aabc-103">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="2aabc-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2aabc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2aabc-104">Methods</span></span>  
  
|<span data-ttu-id="2aabc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2aabc-105">Method</span></span>|<span data-ttu-id="2aabc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2aabc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2aabc-107">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="2aabc-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="2aabc-108">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="2aabc-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="2aabc-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="2aabc-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="2aabc-110">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="2aabc-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="2aabc-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="2aabc-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="2aabc-112">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="2aabc-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aabc-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="2aabc-113">Remarks</span></span>  
 <span data-ttu-id="2aabc-114">Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="2aabc-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2aabc-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2aabc-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="2aabc-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2aabc-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aabc-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2aabc-117">Requirements</span></span>  
 <span data-ttu-id="2aabc-118">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aabc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aabc-119">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2aabc-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2aabc-120">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="2aabc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2aabc-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aabc-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aabc-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2aabc-122">See also</span></span>

- [<span data-ttu-id="2aabc-123">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="2aabc-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="2aabc-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2aabc-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2aabc-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="2aabc-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
