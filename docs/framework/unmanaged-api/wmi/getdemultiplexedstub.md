---
title: Функция GetDemultiplexedStub (Справочник по неуправляемым API)
description: Функция GetDemultiplexedStub создает приемник объект сервера пересылки для помощи в получении асинхронных вызовов из системы управления Windows клиента.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b519ea4062682a56b5b4e277de22b14799f65d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783221"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="ed85e-103">Функция GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="ed85e-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="ed85e-104">Создает приемник переадресации объекта, который помогает клиенту получать асинхронные вызовы из службы управления Windows.</span><span class="sxs-lookup"><span data-stu-id="ed85e-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ed85e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed85e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="ed85e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed85e-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="ed85e-107">[in] Указатель на реализацию в процессе клиента [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="ed85e-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="ed85e-108">[in] Флаг, указывающий, является ли событие локального (`true`); в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="ed85e-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="ed85e-109">[out] Сервер пересылки приемника объектов, для помощи в получении асинхронных вызовов из системы управления Windows клиента.</span><span class="sxs-lookup"><span data-stu-id="ed85e-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="ed85e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ed85e-110">Return value</span></span>

<span data-ttu-id="ed85e-111">Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="ed85e-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="ed85e-112">Если функция завершается с ошибкой, возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed85e-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="ed85e-113">Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="ed85e-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="ed85e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ed85e-114">Requirements</span></span>  
 <span data-ttu-id="ed85e-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed85e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed85e-116">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ed85e-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ed85e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed85e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed85e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ed85e-118">See also</span></span>

- [<span data-ttu-id="ed85e-119">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="ed85e-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
