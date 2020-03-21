---
title: Функция BlessIWbemServicesObject (Неуправляемая справка API)
description: Функция BlessIWbemServicesObject показывает, позволяют ли учетные данные пользователей получить доступ к объекту IWbemServices
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd822f78d29ad3a75fb5e57dd7c23b7049d445b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175035"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="7c192-103">Функция BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="7c192-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="7c192-104">Указывает, позволяют ли учетные данные пользователя получить доступ к указанному объекту [IWbemServices.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)</span><span class="sxs-lookup"><span data-stu-id="7c192-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7c192-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c192-105">Syntax</span></span>

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="7c192-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c192-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="7c192-107">(в) Указатель на объект службы WMI.</span><span class="sxs-lookup"><span data-stu-id="7c192-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="7c192-108">(в) Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c192-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="7c192-109">(в) Пароль, связанный с `strUser`.</span><span class="sxs-lookup"><span data-stu-id="7c192-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="7c192-110">(в) Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c192-110">[in] The domain name of the user.</span></span> <span data-ttu-id="7c192-111">Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="7c192-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="7c192-112">(в) Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="7c192-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="7c192-113">(в) Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="7c192-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="7c192-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7c192-114">Return value</span></span>

<span data-ttu-id="7c192-115">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WinError.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7c192-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7c192-116">Постоянно</span><span class="sxs-lookup"><span data-stu-id="7c192-116">Constant</span></span>  |<span data-ttu-id="7c192-117">Значение</span><span class="sxs-lookup"><span data-stu-id="7c192-117">Value</span></span>  |<span data-ttu-id="7c192-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7c192-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="7c192-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="7c192-119">0x80070057</span></span> | <span data-ttu-id="7c192-120">Один или несколько аргументов недействительны.</span><span class="sxs-lookup"><span data-stu-id="7c192-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="7c192-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="7c192-121">0x80004003</span></span> | <span data-ttu-id="7c192-122">Параметр `pIWbemServices` равен `null`.</span><span class="sxs-lookup"><span data-stu-id="7c192-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="7c192-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="7c192-123">0x80000008</span></span> | <span data-ttu-id="7c192-124">Возникла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7c192-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="7c192-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="7c192-125">0x80000002</span></span> | <span data-ttu-id="7c192-126">Недостаточно памяти доступно для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="7c192-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="7c192-127">0</span><span class="sxs-lookup"><span data-stu-id="7c192-127">0</span></span> | <span data-ttu-id="7c192-128">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="7c192-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="7c192-129">Требования</span><span class="sxs-lookup"><span data-stu-id="7c192-129">Requirements</span></span>

 <span data-ttu-id="7c192-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c192-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="7c192-131">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7c192-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="7c192-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7c192-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7c192-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7c192-133">See also</span></span>

- [<span data-ttu-id="7c192-134">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7c192-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
