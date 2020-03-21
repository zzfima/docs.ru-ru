---
title: Функция GetDemultiplexedStub (Неуправляемая справка API)
description: Функция GetDemultiplexedStub создает поглотитель антока объекта, чтобы помочь клиенту в получении асинхронных звонков от управления Windows.
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174970"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="aa266-103">Функция GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="aa266-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="aa266-104">Создает приемник переадресации объекта, который помогает клиенту получать асинхронные вызовы из службы управления Windows.</span><span class="sxs-lookup"><span data-stu-id="aa266-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="aa266-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa266-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="aa266-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa266-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="aa266-107">(в) Указатель на процесс реализации клиента [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="aa266-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="aa266-108">(в) Флаг, указывающий, является ли`true`событие локальным (); в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="aa266-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="aa266-109">(ваут) Объект-форвард тонет, чтобы помочь клиенту в получении асинхронных звонков от управления Windows.</span><span class="sxs-lookup"><span data-stu-id="aa266-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="aa266-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aa266-110">Return value</span></span>

<span data-ttu-id="aa266-111">Если функция успешно, значение возврата `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="aa266-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="aa266-112">Если функция выходит из строя, значение возврата является ненулевым кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="aa266-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="aa266-113">Чтобы получить расширенную информацию об ошибке, позвоните в функцию [GetErrorInfo.](geterrorinfo.md)</span><span class="sxs-lookup"><span data-stu-id="aa266-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa266-114">Требования</span><span class="sxs-lookup"><span data-stu-id="aa266-114">Requirements</span></span>  
 <span data-ttu-id="aa266-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa266-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa266-116">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="aa266-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="aa266-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa266-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa266-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa266-118">See also</span></span>

- [<span data-ttu-id="aa266-119">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="aa266-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
