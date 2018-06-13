---
title: Функция SetSecurity (Справочник по неуправляемым API)
description: Функция SetSecurity получает маркер олицетворения текущего потока.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fd354e1103832abee7f634eace3dd6defa8b646
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458755"
---
# <a name="setsecurity-function"></a><span data-ttu-id="55ca4-103">Функция SetSecurity</span><span class="sxs-lookup"><span data-stu-id="55ca4-103">SetSecurity function</span></span>
<span data-ttu-id="55ca4-104">Извлекает маркер олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="55ca4-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="55ca4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55ca4-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="55ca4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="55ca4-106">Parameters</span></span>

<span data-ttu-id="55ca4-107">`pNeedToReset` [out] Когда функция возвращает значение, содержит указатель на `boolean` , указывающее, должно ли сбросить токен путем вызова [ResetSecurity](resetsecurity.md) функции.</span><span class="sxs-lookup"><span data-stu-id="55ca4-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="55ca4-108">[out] Когда функция возвращает значение, содержит указатель на дескриптор токена олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="55ca4-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="55ca4-109">Его значение может быть `null` существует ли токен, не связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="55ca4-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="55ca4-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="55ca4-110">Return value</span></span>

<span data-ttu-id="55ca4-111">Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="55ca4-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="55ca4-112">Если функция завершается с ошибкой, возвращается код ошибки ненулевое значение.</span><span class="sxs-lookup"><span data-stu-id="55ca4-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="55ca4-113">Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="55ca4-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="55ca4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="55ca4-114">Requirements</span></span>  
 <span data-ttu-id="55ca4-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55ca4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55ca4-116">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="55ca4-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="55ca4-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="55ca4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ca4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="55ca4-118">See also</span></span>  
[<span data-ttu-id="55ca4-119">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="55ca4-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
