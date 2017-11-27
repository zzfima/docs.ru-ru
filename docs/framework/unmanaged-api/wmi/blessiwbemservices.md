---
title: "Функция BlessIWbemServices (Справочник по неуправляемым API)"
description: "Функция BlessIWbemServices указывает ли учетные данные разрешают доступ к классу IWbemServices."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BlessIWbemServices
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BlessIWbemServices
helpviewer_keywords: BlessIWbemServices function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67431d4272ac1da4d400a5552c61cf464680b502
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="e7bca-103">Функция BlessIWbemServices</span><span class="sxs-lookup"><span data-stu-id="e7bca-103">BlessIWbemServices function</span></span>
<span data-ttu-id="e7bca-104">Указывает, разрешить ли учетные данные пользователя доступ к указанным [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) класса.</span><span class="sxs-lookup"><span data-stu-id="e7bca-104">Indicates whether the user credentials permit access to the specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e7bca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7bca-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="e7bca-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7bca-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="e7bca-107">[in] Указатель на [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) объекта, для которого требуются разрешения.</span><span class="sxs-lookup"><span data-stu-id="e7bca-107">[in] A pointer to the [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="e7bca-108">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7bca-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="e7bca-109">[in] Пароль, связанный с `strUser`.</span><span class="sxs-lookup"><span data-stu-id="e7bca-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="e7bca-110">`strAuthority`[in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7bca-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="e7bca-111">В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="e7bca-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="e7bca-112">`impLevel`[in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="e7bca-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="e7bca-113">`authnLevel`[in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="e7bca-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="e7bca-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7bca-114">Return value</span></span>

<span data-ttu-id="e7bca-115">Следующие значения, возвращаемые этой функцией, определяются в *WinError.h* заголовочный файл, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="e7bca-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e7bca-116">Константа</span><span class="sxs-lookup"><span data-stu-id="e7bca-116">Constant</span></span>  |<span data-ttu-id="e7bca-117">Значение</span><span class="sxs-lookup"><span data-stu-id="e7bca-117">Value</span></span>  |<span data-ttu-id="e7bca-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e7bca-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="e7bca-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="e7bca-119">0x80070057</span></span> | <span data-ttu-id="e7bca-120">Один или несколько аргументов являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="e7bca-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="e7bca-121">отметкой 0x80004003</span><span class="sxs-lookup"><span data-stu-id="e7bca-121">0x80004003</span></span> | <span data-ttu-id="e7bca-122">Свойство `pIWbemServices` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="e7bca-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="e7bca-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="e7bca-123">0x80000008</span></span> | <span data-ttu-id="e7bca-124">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="e7bca-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="e7bca-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="e7bca-125">0x80000002</span></span> | <span data-ttu-id="e7bca-126">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="e7bca-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="e7bca-127">0</span><span class="sxs-lookup"><span data-stu-id="e7bca-127">0</span></span> | <span data-ttu-id="e7bca-128">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="e7bca-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="e7bca-129">Требования</span><span class="sxs-lookup"><span data-stu-id="e7bca-129">Requirements</span></span>  
 <span data-ttu-id="e7bca-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7bca-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7bca-131">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e7bca-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e7bca-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e7bca-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7bca-133">См. также</span><span class="sxs-lookup"><span data-stu-id="e7bca-133">See also</span></span>  
[<span data-ttu-id="e7bca-134">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e7bca-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
