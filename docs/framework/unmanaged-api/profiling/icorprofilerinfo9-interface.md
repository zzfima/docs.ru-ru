---
title: Интерфейс ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: af6bd02c6d4e88c72dca20d2520d1ecc8cf1c421
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928788"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="a85ff-102">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="a85ff-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="a85ff-103">Подкласс [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) , предоставляющий методы для запроса сведений о функциях с несколькими версиями машинного кода.</span><span class="sxs-lookup"><span data-stu-id="a85ff-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="a85ff-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a85ff-104">Methods</span></span>  

| <span data-ttu-id="a85ff-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a85ff-105">Method</span></span>|<span data-ttu-id="a85ff-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a85ff-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="a85ff-107">Метод Жетнативекодестартаддрессес</span><span class="sxs-lookup"><span data-stu-id="a85ff-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="a85ff-108">При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют.</span><span class="sxs-lookup"><span data-stu-id="a85ff-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="a85ff-109">Метод GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="a85ff-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="a85ff-110">С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.</span><span class="sxs-lookup"><span data-stu-id="a85ff-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="a85ff-111">Метод GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="a85ff-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="a85ff-112">При наличии начального адреса машинного кода возвращает блоки виртуальной памяти, в которых хранится этот код.</span><span class="sxs-lookup"><span data-stu-id="a85ff-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="a85ff-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a85ff-113">Requirements</span></span>  
<span data-ttu-id="a85ff-114">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="a85ff-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="a85ff-115">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a85ff-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="a85ff-116">**Версии .NET:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a85ff-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a85ff-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a85ff-117">See also</span></span>

- [<span data-ttu-id="a85ff-118">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="a85ff-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
