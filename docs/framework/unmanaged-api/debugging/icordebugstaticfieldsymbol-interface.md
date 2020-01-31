---
title: Интерфейс ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: b50b9c8435f19e1a77229f01dc85514f5f75c9f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791803"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="e2171-102">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e2171-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="e2171-103">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="e2171-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2171-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e2171-104">Methods</span></span>  
  
|<span data-ttu-id="e2171-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e2171-105">Method</span></span>|<span data-ttu-id="e2171-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e2171-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2171-107">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="e2171-107">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="e2171-108">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="e2171-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="e2171-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="e2171-109">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="e2171-110">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="e2171-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="e2171-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="e2171-111">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="e2171-112">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="e2171-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2171-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="e2171-113">Remarks</span></span>  
 <span data-ttu-id="e2171-114">Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="e2171-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2171-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e2171-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e2171-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e2171-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2171-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e2171-117">Requirements</span></span>  
 <span data-ttu-id="e2171-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2171-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2171-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2171-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2171-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2171-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2171-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2171-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2171-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2171-122">See also</span></span>

- [<span data-ttu-id="e2171-123">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e2171-123">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="e2171-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e2171-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e2171-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="e2171-125">Debugging</span></span>](index.md)
