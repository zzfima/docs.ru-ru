---
title: Функция Set Security (Неуправляемая справка API)
description: Функция SetSecurity извлекает токен олицетворения текущего потока.
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
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176738"
---
# <a name="setsecurity-function"></a><span data-ttu-id="723a2-103">Функция SetSecurity</span><span class="sxs-lookup"><span data-stu-id="723a2-103">SetSecurity function</span></span>

<span data-ttu-id="723a2-104">Получает маркер олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="723a2-104">Retrieves the impersonation token associated with the current thread.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="723a2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="723a2-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a><span data-ttu-id="723a2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="723a2-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="723a2-107">(ваут) При возврате функции содержится `boolean` указатель на указатель, указывающий, следует ли сбросить маркер, вызывая функцию [ResetSecurity.](resetsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="723a2-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="723a2-108">(ваут) Когда функция возвращается, содержит указатель на ручку маркера олицетворения, связанного с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="723a2-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="723a2-109">Его значение `null` может быть, если нет маркера, связанного с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="723a2-109">Its value can be `null` if there is no token associated with the current thread.</span></span>

## <a name="return-value"></a><span data-ttu-id="723a2-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="723a2-110">Return value</span></span>

<span data-ttu-id="723a2-111">Если функция успешно, значение возврата `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="723a2-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="723a2-112">Если функция выходит из строя, значение возврата является ненулевым кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="723a2-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="723a2-113">Чтобы получить расширенную информацию об ошибке, позвоните в функцию [GetErrorInfo.](geterrorinfo.md)</span><span class="sxs-lookup"><span data-stu-id="723a2-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="723a2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="723a2-114">Requirements</span></span>

 <span data-ttu-id="723a2-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="723a2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="723a2-116">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="723a2-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="723a2-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="723a2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="723a2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="723a2-118">See also</span></span>

- [<span data-ttu-id="723a2-119">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="723a2-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
