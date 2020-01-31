---
title: Интерфейс ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: deb300ced2ff7a116bd443c9a7b10dcc0b7955ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784530"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="3c915-102">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="3c915-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="3c915-103">Логически расширяет интерфейс ICorDebugAssembly для обеспечения поддержки контейнерных сборок и их вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="3c915-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c915-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3c915-104">Methods</span></span>  
  
|<span data-ttu-id="3c915-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3c915-105">Method</span></span>|<span data-ttu-id="3c915-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3c915-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c915-107">Метод EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="3c915-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="3c915-108">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="3c915-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="3c915-109">Метод GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="3c915-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="3c915-110">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="3c915-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c915-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="3c915-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c915-112">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3c915-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="3c915-113">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3c915-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c915-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3c915-114">Requirements</span></span>  
 <span data-ttu-id="3c915-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c915-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c915-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c915-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c915-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c915-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c915-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c915-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c915-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c915-119">See also</span></span>

- [<span data-ttu-id="3c915-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3c915-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3c915-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="3c915-121">Debugging</span></span>](index.md)
