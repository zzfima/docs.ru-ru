---
title: Функция EndEnumeration (Справочник по неуправляемым API)
description: Функция EndEnumeration завершает перечисления.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5c576cb808ee92452c193c3fbce4f1d2c2cad05
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636772"
---
# <a name="endenumeration-function"></a><span data-ttu-id="951b3-103">Функция EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="951b3-103">EndEnumeration function</span></span>

<span data-ttu-id="951b3-104">Завершает работу вызовом последовательности перечисления [функция BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="951b3-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="951b3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="951b3-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="951b3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="951b3-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="951b3-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="951b3-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="951b3-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="951b3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="951b3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="951b3-109">Return value</span></span>

<span data-ttu-id="951b3-110">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="951b3-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="951b3-111">Константа</span><span class="sxs-lookup"><span data-stu-id="951b3-111">Constant</span></span>  |<span data-ttu-id="951b3-112">Значение</span><span class="sxs-lookup"><span data-stu-id="951b3-112">Value</span></span>  |<span data-ttu-id="951b3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="951b3-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="951b3-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="951b3-114">0x80041001</span></span> | <span data-ttu-id="951b3-115">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="951b3-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="951b3-116">0</span><span class="sxs-lookup"><span data-stu-id="951b3-116">0</span></span> | <span data-ttu-id="951b3-117">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="951b3-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="951b3-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="951b3-118">Remarks</span></span>

<span data-ttu-id="951b3-119">Эта функция создает оболочку для вызова [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) метод.</span><span class="sxs-lookup"><span data-stu-id="951b3-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="951b3-120">Вызов `EndEnumeration` функция не является обязательным, но рекомендуется, так как он освобождает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="951b3-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="951b3-121">Однако ресурсы освобождаются автоматически при запуске следующего перечисления или объект освобождается.</span><span class="sxs-lookup"><span data-stu-id="951b3-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="951b3-122">Требования</span><span class="sxs-lookup"><span data-stu-id="951b3-122">Requirements</span></span>

<span data-ttu-id="951b3-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="951b3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="951b3-124">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="951b3-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="951b3-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="951b3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="951b3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="951b3-126">See also</span></span>

- [<span data-ttu-id="951b3-127">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="951b3-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
