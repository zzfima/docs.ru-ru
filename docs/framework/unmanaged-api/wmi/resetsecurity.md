---
title: "Функция ResetSecurity (Справочник по неуправляемым API)"
description: "Функция ResetSecurity назначает маркер олицетворения текущего потока."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ResetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ResetSecurity
helpviewer_keywords: ResetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2790012a429c6a0551d8321a80570f3f8be2142b
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="resetsecurity-function"></a><span data-ttu-id="df27d-103">Функция ResetSecurity</span><span class="sxs-lookup"><span data-stu-id="df27d-103">ResetSecurity function</span></span>
<span data-ttu-id="df27d-104">Присваивает указанный олицетворения текущего потока.</span><span class="sxs-lookup"><span data-stu-id="df27d-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="df27d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df27d-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="df27d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="df27d-106">Parameters</span></span>

`token`  
<span data-ttu-id="df27d-107">[in] Токен олицетворения для связывания с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="df27d-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="df27d-108">Это значение может быть равно `null`.</span><span class="sxs-lookup"><span data-stu-id="df27d-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="df27d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df27d-109">Return value</span></span>

<span data-ttu-id="df27d-110">Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="df27d-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="df27d-111">Если функция завершается с ошибкой, возвращается код ошибки ненулевое значение.</span><span class="sxs-lookup"><span data-stu-id="df27d-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="df27d-112">Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="df27d-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="df27d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="df27d-113">Requirements</span></span>  
 <span data-ttu-id="df27d-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df27d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df27d-115">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="df27d-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="df27d-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="df27d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df27d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="df27d-117">See also</span></span>  
[<span data-ttu-id="df27d-118">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="df27d-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
