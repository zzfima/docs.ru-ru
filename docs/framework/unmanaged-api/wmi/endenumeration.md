---
title: Функция EndEnumeration (Справочник по неуправляемым API)
description: Функция EndEnumeration завершает перечисление.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b9fd1f094c8fb56c94421a07437aa25a3549c487
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132043"
---
# <a name="endenumeration-function"></a><span data-ttu-id="87989-103">Функция EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="87989-103">EndEnumeration function</span></span>

<span data-ttu-id="87989-104">Завершает последовательность перечисления, запущенную с вызовом [функции BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="87989-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="87989-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87989-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="87989-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="87989-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="87989-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="87989-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="87989-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="87989-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="87989-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="87989-109">Return value</span></span>

<span data-ttu-id="87989-110">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="87989-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="87989-111">Константа</span><span class="sxs-lookup"><span data-stu-id="87989-111">Constant</span></span>  |<span data-ttu-id="87989-112">значения</span><span class="sxs-lookup"><span data-stu-id="87989-112">Value</span></span>  |<span data-ttu-id="87989-113">Описание</span><span class="sxs-lookup"><span data-stu-id="87989-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="87989-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="87989-114">0x80041001</span></span> | <span data-ttu-id="87989-115">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="87989-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="87989-116">0</span><span class="sxs-lookup"><span data-stu-id="87989-116">0</span></span> | <span data-ttu-id="87989-117">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="87989-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="87989-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="87989-118">Remarks</span></span>

<span data-ttu-id="87989-119">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="87989-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="87989-120">Вызов функции `EndEnumeration` не требуется, но рекомендуется, так как он освобождает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="87989-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="87989-121">Однако ресурсы освобождаются автоматически при запуске следующего перечисления или при освобождении объекта.</span><span class="sxs-lookup"><span data-stu-id="87989-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="87989-122">Требования</span><span class="sxs-lookup"><span data-stu-id="87989-122">Requirements</span></span>

<span data-ttu-id="87989-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87989-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="87989-124">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="87989-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="87989-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87989-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="87989-126">См. также</span><span class="sxs-lookup"><span data-stu-id="87989-126">See also</span></span>

- [<span data-ttu-id="87989-127">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="87989-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
