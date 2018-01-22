---
title: "Функция GetDemultiplexedStub (Справочник по неуправляемым API)"
description: "Функция GetDemultiplexedStub создает приемника объектов сервера пересылки для клиента при получении асинхронные вызовы от управления Windows."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetDemultiplexedStub
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetDemultiplexedStub
helpviewer_keywords: GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f53ee18345347f506a404a22bf5bfea6af037463
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="a5eac-103">Функция GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="a5eac-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="a5eac-104">Создает приемник объект сервера пересылки для клиента при получении асинхронные вызовы от управления Windows.</span><span class="sxs-lookup"><span data-stu-id="a5eac-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a5eac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5eac-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="a5eac-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5eac-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="a5eac-107">[in] Указатель на реализацию клиента в процессе [IWbemObjectSink](https://msdn.microsoft.com/library/aa391787(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="a5eac-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](https://msdn.microsoft.com/library/aa391787(v=vs.85).aspx).</span></span>

`isLocal`  
<span data-ttu-id="a5eac-108">[in] Флаг, который указывает, является ли событие локального (`true`); в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="a5eac-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="a5eac-109">[out] Объект сервера пересылки приемник для клиента при получении асинхронные вызовы от управления Windows.</span><span class="sxs-lookup"><span data-stu-id="a5eac-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="a5eac-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a5eac-110">Return value</span></span>

<span data-ttu-id="a5eac-111">Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="a5eac-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="a5eac-112">Если функция завершается с ошибкой, возвращается код ошибки ненулевое значение.</span><span class="sxs-lookup"><span data-stu-id="a5eac-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="a5eac-113">Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="a5eac-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="a5eac-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a5eac-114">Requirements</span></span>  
 <span data-ttu-id="a5eac-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5eac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5eac-116">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a5eac-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a5eac-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a5eac-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5eac-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a5eac-118">See also</span></span>  
[<span data-ttu-id="a5eac-119">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="a5eac-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
