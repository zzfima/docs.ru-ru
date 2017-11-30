---
title: "Функция SetSecurity (Справочник по неуправляемым API)"
description: "Функция SetSecurity получает маркер олицетворения текущего потока."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SetSecurity
helpviewer_keywords: SetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4fd7ccb0cfb25773da7e489f9ce4d6332b80a616
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="setsecurity-function"></a><span data-ttu-id="b3c92-103">Функция SetSecurity</span><span class="sxs-lookup"><span data-stu-id="b3c92-103">SetSecurity function</span></span>
<span data-ttu-id="b3c92-104">Извлекает маркер олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="b3c92-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b3c92-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3c92-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="b3c92-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3c92-106">Parameters</span></span>

<span data-ttu-id="b3c92-107">`pNeedToReset`[out] Когда функция возвращает значение, содержит указатель на `boolean` , указывающее, должно ли сбросить токен путем вызова [ResetSecurity](resetsecurity.md) функции.</span><span class="sxs-lookup"><span data-stu-id="b3c92-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="b3c92-108">[out] Когда функция возвращает значение, содержит указатель на дескриптор токена олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="b3c92-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="b3c92-109">Его значение может быть `null` существует ли токен, не связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="b3c92-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="b3c92-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3c92-110">Return value</span></span>

<span data-ttu-id="b3c92-111">Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="b3c92-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="b3c92-112">Если функция завершается с ошибкой, возвращается код ошибки ненулевое значение.</span><span class="sxs-lookup"><span data-stu-id="b3c92-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="b3c92-113">Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="b3c92-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="b3c92-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b3c92-114">Requirements</span></span>  
 <span data-ttu-id="b3c92-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3c92-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c92-116">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b3c92-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b3c92-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b3c92-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c92-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b3c92-118">See also</span></span>  
[<span data-ttu-id="b3c92-119">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="b3c92-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
