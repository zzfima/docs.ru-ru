---
title: Интерфейс ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 0ba4f2b4a515143d50bc812f04ea75d821b69471
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973804"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="27d03-102">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="27d03-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="27d03-103">Подкласс [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) , предоставляющий методы для запроса сведений о функциях с несколькими версиями машинного кода.</span><span class="sxs-lookup"><span data-stu-id="27d03-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="27d03-104">Методы</span><span class="sxs-lookup"><span data-stu-id="27d03-104">Methods</span></span>  

| <span data-ttu-id="27d03-105">Метод</span><span class="sxs-lookup"><span data-stu-id="27d03-105">Method</span></span>|<span data-ttu-id="27d03-106">Описание</span><span class="sxs-lookup"><span data-stu-id="27d03-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="27d03-107">Метод Жетнативекодестартаддрессес</span><span class="sxs-lookup"><span data-stu-id="27d03-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="27d03-108">При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют.</span><span class="sxs-lookup"><span data-stu-id="27d03-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="27d03-109">Метод GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="27d03-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="27d03-110">С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.</span><span class="sxs-lookup"><span data-stu-id="27d03-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="27d03-111">Метод GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="27d03-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="27d03-112">При наличии начального адреса машинного кода возвращает блоки виртуальной памяти, в которых хранится этот код.</span><span class="sxs-lookup"><span data-stu-id="27d03-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="27d03-113">Требования</span><span class="sxs-lookup"><span data-stu-id="27d03-113">Requirements</span></span>  
<span data-ttu-id="27d03-114">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="27d03-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="27d03-115">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="27d03-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="27d03-116">**Версии .NET:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27d03-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="27d03-117">См. также</span><span class="sxs-lookup"><span data-stu-id="27d03-117">See also</span></span>
- [<span data-ttu-id="27d03-118">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="27d03-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
