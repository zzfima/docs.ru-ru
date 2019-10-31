---
title: Функция Блессивбемсервицес (Справочник по неуправляемым API)
description: Функция Блессивбемсервицес указывает, допускают ли учетные данные пользователя доступ к классу IWbemServices.
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
ms.openlocfilehash: 946d29892052ea69c2a8a3bf11e7be7a1b2d7068
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138783"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="4d70a-103">Функция BlessIWbemServices</span><span class="sxs-lookup"><span data-stu-id="4d70a-103">BlessIWbemServices function</span></span>
<span data-ttu-id="4d70a-104">Указывает, допускают ли учетные данные пользователя доступ к указанному классу [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) .</span><span class="sxs-lookup"><span data-stu-id="4d70a-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4d70a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d70a-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="4d70a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d70a-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="4d70a-107">окне Указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , для которого требуются разрешения.</span><span class="sxs-lookup"><span data-stu-id="4d70a-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="4d70a-108">окне Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="4d70a-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="4d70a-109">окне Пароль, связанный с `strUser`.</span><span class="sxs-lookup"><span data-stu-id="4d70a-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="4d70a-110">окне Доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="4d70a-110">[in] The domain name of the user.</span></span> <span data-ttu-id="4d70a-111">Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="4d70a-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="4d70a-112">окне Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="4d70a-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="4d70a-113">окне Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="4d70a-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="4d70a-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4d70a-114">Return value</span></span>

<span data-ttu-id="4d70a-115">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *Winerror. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="4d70a-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4d70a-116">Константа</span><span class="sxs-lookup"><span data-stu-id="4d70a-116">Constant</span></span>  |<span data-ttu-id="4d70a-117">значения</span><span class="sxs-lookup"><span data-stu-id="4d70a-117">Value</span></span>  |<span data-ttu-id="4d70a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="4d70a-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="4d70a-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="4d70a-119">0x80070057</span></span> | <span data-ttu-id="4d70a-120">Один или несколько аргументов недопустимы.</span><span class="sxs-lookup"><span data-stu-id="4d70a-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="4d70a-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="4d70a-121">0x80004003</span></span> | <span data-ttu-id="4d70a-122">Свойство `pIWbemServices` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="4d70a-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="4d70a-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="4d70a-123">0x80000008</span></span> | <span data-ttu-id="4d70a-124">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4d70a-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="4d70a-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="4d70a-125">0x80000002</span></span> | <span data-ttu-id="4d70a-126">Недостаточно свободной памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="4d70a-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="4d70a-127">0</span><span class="sxs-lookup"><span data-stu-id="4d70a-127">0</span></span> | <span data-ttu-id="4d70a-128">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="4d70a-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="4d70a-129">Требования</span><span class="sxs-lookup"><span data-stu-id="4d70a-129">Requirements</span></span>  

 <span data-ttu-id="4d70a-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d70a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d70a-131">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="4d70a-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4d70a-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4d70a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d70a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4d70a-133">See also</span></span>

- [<span data-ttu-id="4d70a-134">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="4d70a-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
