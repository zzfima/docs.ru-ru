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
ms.openlocfilehash: a2cb71263201c86a93ca0bfbd783f2b8512055e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783116"
---
# <a name="setsecurity-function"></a><span data-ttu-id="3363c-103">Функция SetSecurity</span><span class="sxs-lookup"><span data-stu-id="3363c-103">SetSecurity function</span></span>

<span data-ttu-id="3363c-104">Получает маркер олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="3363c-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3363c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3363c-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="3363c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3363c-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="3363c-107">[out] При возврате функции, содержит указатель на `boolean` , указывающее, следует ли сбросить маркер путем вызова [ResetSecurity](resetsecurity.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3363c-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="3363c-108">[out] При возврате функции, содержит указатель на дескриптор токена олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="3363c-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="3363c-109">Его значение может быть `null` имеется ли токен, не связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="3363c-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="3363c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3363c-110">Return value</span></span>

<span data-ttu-id="3363c-111">Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="3363c-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="3363c-112">Если функция завершается с ошибкой, возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3363c-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="3363c-113">Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3363c-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="3363c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3363c-114">Requirements</span></span>

 <span data-ttu-id="3363c-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3363c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="3363c-116">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3363c-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="3363c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3363c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3363c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3363c-118">See also</span></span>

- [<span data-ttu-id="3363c-119">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="3363c-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
