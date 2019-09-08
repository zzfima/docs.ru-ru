---
title: Функция Сетсекурити (Справочник по неуправляемым API)
description: Функция Сетсекурити Извлекает токен олицетворения текущего потока.
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
ms.openlocfilehash: 94c76213acb66116105d181e9961a33976047ee7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798248"
---
# <a name="setsecurity-function"></a><span data-ttu-id="11e2c-103">Функция Сетсекурити</span><span class="sxs-lookup"><span data-stu-id="11e2c-103">SetSecurity function</span></span>

<span data-ttu-id="11e2c-104">Получает маркер олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="11e2c-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="11e2c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11e2c-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="11e2c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="11e2c-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="11e2c-107">заполняет При возврате функции содержит указатель на `boolean` , указывающий, следует ли сбрасывать маркер путем вызова функции [ресетсекурити](resetsecurity.md) .</span><span class="sxs-lookup"><span data-stu-id="11e2c-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="11e2c-108">заполняет При возврате функции содержит указатель на маркер маркера олицетворения, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="11e2c-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="11e2c-109">Его значение может быть `null` , если нет токена, связанного с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="11e2c-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="11e2c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11e2c-110">Return value</span></span>

<span data-ttu-id="11e2c-111">Если функция выполнена, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="11e2c-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="11e2c-112">Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="11e2c-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="11e2c-113">Чтобы получить расширенные сведения об ошибке, вызовите функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="11e2c-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="11e2c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="11e2c-114">Requirements</span></span>

 <span data-ttu-id="11e2c-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11e2c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="11e2c-116">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="11e2c-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="11e2c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="11e2c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="11e2c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="11e2c-118">See also</span></span>

- [<span data-ttu-id="11e2c-119">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="11e2c-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
