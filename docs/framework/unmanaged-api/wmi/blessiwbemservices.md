---
title: Функция BlessIWbemServices (Неуправляемая справка API)
description: Функция BlessIWbemServices указывает, позволяют ли учетные данные пользователей получить доступ к классу IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4b15af840cc00b3ec261604db4f3625c6b975d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176868"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="4b01a-103">Функция BlessIWbemServices</span><span class="sxs-lookup"><span data-stu-id="4b01a-103">BlessIWbemServices function</span></span>
<span data-ttu-id="4b01a-104">Указывает, позволяют ли учетные данные пользователя получить доступ к указанному классу [IWbemServices.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)</span><span class="sxs-lookup"><span data-stu-id="4b01a-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4b01a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b01a-105">Syntax</span></span>  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="4b01a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b01a-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="4b01a-107">(в) Указатель на объект [IWbemServices,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) для которого требуются разрешения.</span><span class="sxs-lookup"><span data-stu-id="4b01a-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="4b01a-108">(в) Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b01a-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="4b01a-109">(в) Пароль, связанный с `strUser`.</span><span class="sxs-lookup"><span data-stu-id="4b01a-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="4b01a-110">(в) Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b01a-110">[in] The domain name of the user.</span></span> <span data-ttu-id="4b01a-111">Дополнительную информацию можно узнать из функции [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="4b01a-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="4b01a-112">(в) Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="4b01a-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="4b01a-113">(в) Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="4b01a-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="4b01a-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b01a-114">Return value</span></span>

<span data-ttu-id="4b01a-115">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WinError.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="4b01a-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4b01a-116">Постоянно</span><span class="sxs-lookup"><span data-stu-id="4b01a-116">Constant</span></span>  |<span data-ttu-id="4b01a-117">Значение</span><span class="sxs-lookup"><span data-stu-id="4b01a-117">Value</span></span>  |<span data-ttu-id="4b01a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="4b01a-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="4b01a-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="4b01a-119">0x80070057</span></span> | <span data-ttu-id="4b01a-120">Один или несколько аргументов недействительны.</span><span class="sxs-lookup"><span data-stu-id="4b01a-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="4b01a-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="4b01a-121">0x80004003</span></span> | <span data-ttu-id="4b01a-122">Параметр `pIWbemServices` равен `null`.</span><span class="sxs-lookup"><span data-stu-id="4b01a-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="4b01a-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="4b01a-123">0x80000008</span></span> | <span data-ttu-id="4b01a-124">Возникла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4b01a-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="4b01a-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="4b01a-125">0x80000002</span></span> | <span data-ttu-id="4b01a-126">Недостаточно памяти доступно для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="4b01a-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="4b01a-127">0</span><span class="sxs-lookup"><span data-stu-id="4b01a-127">0</span></span> | <span data-ttu-id="4b01a-128">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="4b01a-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4b01a-129">Требования</span><span class="sxs-lookup"><span data-stu-id="4b01a-129">Requirements</span></span>  

 <span data-ttu-id="4b01a-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b01a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b01a-131">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4b01a-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4b01a-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4b01a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b01a-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4b01a-133">See also</span></span>

- [<span data-ttu-id="4b01a-134">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="4b01a-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
