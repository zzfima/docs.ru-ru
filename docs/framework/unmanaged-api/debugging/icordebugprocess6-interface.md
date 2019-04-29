---
title: Интерфейс ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518c6ec99e4062bf8432809d3472baa395017da3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948629"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="3a3f4-102">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="3a3f4-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="3a3f4-103">Логически расширяет интерфейс ICorDebugProcess для включения функций, таких как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a3f4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3a3f4-104">Methods</span></span>  
  
|<span data-ttu-id="3a3f4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3a3f4-105">Method</span></span>|<span data-ttu-id="3a3f4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3a3f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a3f4-107">Метод DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="3a3f4-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="3a3f4-108">Декодирует события управляемой отладки, которые были инкапсулированы в полезную нагрузку из событий отладки специально созданных собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="3a3f4-109">Метод EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="3a3f4-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="3a3f4-110">Позволяет включить или отключить разделение виртуальных модулей.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="3a3f4-111">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="3a3f4-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="3a3f4-112">Получает информацию об управляемом коде по адресу определенного кода.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="3a3f4-113">Метод GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="3a3f4-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="3a3f4-114">Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="3a3f4-115">Метод MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="3a3f4-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="3a3f4-116">Изменяет внутреннее состояние отлаживаемого кода таким образом, что метод <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> в библиотеке классов платформы .NET Framework возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="3a3f4-117">Метод ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="3a3f4-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="3a3f4-118">Уведомляет [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a3f4-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a3f4-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a3f4-120">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="3a3f4-121">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3a3f4-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a3f4-122">Требования</span><span class="sxs-lookup"><span data-stu-id="3a3f4-122">Requirements</span></span>  
 <span data-ttu-id="3a3f4-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a3f4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a3f4-124">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a3f4-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a3f4-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a3f4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a3f4-126">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a3f4-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a3f4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3a3f4-127">See also</span></span>

- [<span data-ttu-id="3a3f4-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3a3f4-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3a3f4-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="3a3f4-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
