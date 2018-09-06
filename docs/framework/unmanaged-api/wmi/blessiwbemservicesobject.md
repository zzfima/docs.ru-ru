---
title: Функция BlessIWbemServicesObject (Справочник по неуправляемым API)
description: Функция BlessIWbemServicesObject указывает, разрешить ли учетные данные пользователя доступ к объекту IWbemServices
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
ms.openlocfilehash: e1380d03d4456e0695777775ae786a19982d691b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864411"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="2d0ca-103">Функция BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="2d0ca-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="2d0ca-104">Указывает, разрешить ли учетные данные пользователя доступом к заданному [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) объекта.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2d0ca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d0ca-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="2d0ca-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d0ca-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="2d0ca-107">[in] Указатель на объект службы WMI.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-107">[in] A pointer to a WMI service object.</span></span>

`strUser`  
<span data-ttu-id="2d0ca-108">[in] Имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="2d0ca-109">[in] Пароль, связанный с `strUser`.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="2d0ca-110">`strAuthority` [in] Имя домена пользователя.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="2d0ca-111">См. в разделе [ConnectServerWmi](connectserverwmi.md) функции подробнее.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="2d0ca-112">`impLevel` [in] Уровень олицетворения.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="2d0ca-113">`authnLevel` [in] Уровень авторизации.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="2d0ca-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2d0ca-114">Return value</span></span>

<span data-ttu-id="2d0ca-115">Следующие значения, возвращаемые этой функцией, определяются в *WinError.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="2d0ca-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2d0ca-116">Константа</span><span class="sxs-lookup"><span data-stu-id="2d0ca-116">Constant</span></span>  |<span data-ttu-id="2d0ca-117">Значение</span><span class="sxs-lookup"><span data-stu-id="2d0ca-117">Value</span></span>  |<span data-ttu-id="2d0ca-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2d0ca-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="2d0ca-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="2d0ca-119">0x80070057</span></span> | <span data-ttu-id="2d0ca-120">Один или несколько аргументов являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="2d0ca-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="2d0ca-121">0x80004003</span></span> | <span data-ttu-id="2d0ca-122">Свойство `pIWbemServices` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="2d0ca-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="2d0ca-123">0x80000008</span></span> | <span data-ttu-id="2d0ca-124">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="2d0ca-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="2d0ca-125">0x80000002</span></span> | <span data-ttu-id="2d0ca-126">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="2d0ca-127">0</span><span class="sxs-lookup"><span data-stu-id="2d0ca-127">0</span></span> | <span data-ttu-id="2d0ca-128">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="2d0ca-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="2d0ca-129">Требования</span><span class="sxs-lookup"><span data-stu-id="2d0ca-129">Requirements</span></span>  
 <span data-ttu-id="2d0ca-130">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d0ca-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d0ca-131">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2d0ca-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2d0ca-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d0ca-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d0ca-133">См. также</span><span class="sxs-lookup"><span data-stu-id="2d0ca-133">See also</span></span>  
[<span data-ttu-id="2d0ca-134">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="2d0ca-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
