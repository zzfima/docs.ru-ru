---
title: Функция Блессивбемсервицесобжект (Справочник по неуправляемым API)
description: Функция Блессивбемсервицесобжект указывает, допускают ли учетные данные пользователя доступ к объекту IWbemServices.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94c6f47e67cf22f189719a8a9f56e830ee90227c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798725"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="d7741-103">Функция BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="d7741-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="d7741-104">Указывает, допускают ли учетные данные пользователя доступ к указанному объекту [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) .</span><span class="sxs-lookup"><span data-stu-id="d7741-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d7741-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7741-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="d7741-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7741-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="d7741-107">окне Указатель на объект службы WMI.</span><span class="sxs-lookup"><span data-stu-id="d7741-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="d7741-108">окне Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7741-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="d7741-109">окне Пароль, связанный с `strUser`.</span><span class="sxs-lookup"><span data-stu-id="d7741-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="d7741-110">окне Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7741-110">[in] The domain name of the user.</span></span> <span data-ttu-id="d7741-111">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="d7741-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="d7741-112">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="d7741-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="d7741-113">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="d7741-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="d7741-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7741-114">Return value</span></span>

<span data-ttu-id="d7741-115">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *Winerror. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="d7741-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d7741-116">Константа</span><span class="sxs-lookup"><span data-stu-id="d7741-116">Constant</span></span>  |<span data-ttu-id="d7741-117">Значение</span><span class="sxs-lookup"><span data-stu-id="d7741-117">Value</span></span>  |<span data-ttu-id="d7741-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d7741-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="d7741-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="d7741-119">0x80070057</span></span> | <span data-ttu-id="d7741-120">Один или несколько аргументов недопустимы.</span><span class="sxs-lookup"><span data-stu-id="d7741-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="d7741-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="d7741-121">0x80004003</span></span> | <span data-ttu-id="d7741-122">Свойство `pIWbemServices` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="d7741-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="d7741-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="d7741-123">0x80000008</span></span> | <span data-ttu-id="d7741-124">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d7741-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="d7741-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="d7741-125">0x80000002</span></span> | <span data-ttu-id="d7741-126">Недостаточно свободной памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="d7741-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="d7741-127">0</span><span class="sxs-lookup"><span data-stu-id="d7741-127">0</span></span> | <span data-ttu-id="d7741-128">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="d7741-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="d7741-129">Требования</span><span class="sxs-lookup"><span data-stu-id="d7741-129">Requirements</span></span>

 <span data-ttu-id="d7741-130">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7741-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="d7741-131">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="d7741-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="d7741-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d7741-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d7741-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d7741-133">See also</span></span>

- [<span data-ttu-id="d7741-134">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="d7741-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
