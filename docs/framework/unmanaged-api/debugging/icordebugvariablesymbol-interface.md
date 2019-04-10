---
title: Интерфейс ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c7cdababd1e4b5fae4f5e48a654f861b708a6e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226564"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="f343a-102">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f343a-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="f343a-103">Извлекает сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="f343a-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f343a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f343a-104">Methods</span></span>  
  
|<span data-ttu-id="f343a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f343a-105">Method</span></span>|<span data-ttu-id="f343a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f343a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f343a-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="f343a-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="f343a-108">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f343a-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="f343a-109">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="f343a-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="f343a-110">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="f343a-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="f343a-111">Метод GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="f343a-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="f343a-112">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="f343a-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="f343a-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="f343a-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="f343a-114">Возвращает значение переменной в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="f343a-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="f343a-115">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="f343a-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="f343a-116">Присваивает переменной значение массива байтов.</span><span class="sxs-lookup"><span data-stu-id="f343a-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f343a-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f343a-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f343a-118">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f343a-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f343a-119">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f343a-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f343a-120">Требования</span><span class="sxs-lookup"><span data-stu-id="f343a-120">Requirements</span></span>  
 <span data-ttu-id="f343a-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f343a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f343a-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f343a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f343a-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f343a-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f343a-124">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f343a-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f343a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f343a-125">See also</span></span>

- [<span data-ttu-id="f343a-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f343a-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f343a-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="f343a-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
