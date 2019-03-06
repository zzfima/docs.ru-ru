---
title: Функция GetMethodQualifierSet (Справочник по неуправляемым API)
description: Функция GetMethodQualifierSet извлекает набор описателей метода.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9257ba57e0d087e3d6b9c7bb995b49a6b814c5f1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373612"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="fdca3-103">Функция GetMethodQualifierSet</span><span class="sxs-lookup"><span data-stu-id="fdca3-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="fdca3-104">Получает набор квалификаторов для определенного метода.</span><span class="sxs-lookup"><span data-stu-id="fdca3-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fdca3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdca3-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="fdca3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fdca3-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="fdca3-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="fdca3-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="fdca3-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fdca3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="fdca3-109">[in] Имя метода.</span><span class="sxs-lookup"><span data-stu-id="fdca3-109">[in] The method  name.</span></span> <span data-ttu-id="fdca3-110">`wszMethod` должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="fdca3-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="fdca3-111">[out] Получает указатель интерфейса, которое разрешает доступ к квалификаторы метода.</span><span class="sxs-lookup"><span data-stu-id="fdca3-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="fdca3-112">Параметр `ppQualSet` не может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="fdca3-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="fdca3-113">Если возникает ошибка, не возвращается новый объект и указатель имеет значение для указания `null`.</span><span class="sxs-lookup"><span data-stu-id="fdca3-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="fdca3-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fdca3-114">Return value</span></span>

<span data-ttu-id="fdca3-115">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="fdca3-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fdca3-116">Константа</span><span class="sxs-lookup"><span data-stu-id="fdca3-116">Constant</span></span>  |<span data-ttu-id="fdca3-117">Значение</span><span class="sxs-lookup"><span data-stu-id="fdca3-117">Value</span></span>  |<span data-ttu-id="fdca3-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="fdca3-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="fdca3-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="fdca3-119">0x80041002</span></span> | <span data-ttu-id="fdca3-120">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="fdca3-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fdca3-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fdca3-121">0x80041008</span></span> | <span data-ttu-id="fdca3-122">Параметр — `null`.</span><span class="sxs-lookup"><span data-stu-id="fdca3-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fdca3-123">0</span><span class="sxs-lookup"><span data-stu-id="fdca3-123">0</span></span> | <span data-ttu-id="fdca3-124">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="fdca3-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="fdca3-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="fdca3-125">Remarks</span></span>

<span data-ttu-id="fdca3-126">Эта функция создает оболочку для вызова [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) метод.</span><span class="sxs-lookup"><span data-stu-id="fdca3-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="fdca3-127">Вызов этой функции поддерживается только в том случае, если текущий объект является определение класса CIM.</span><span class="sxs-lookup"><span data-stu-id="fdca3-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="fdca3-128">Метод манипуляции не доступен для [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указатели, которые указывают на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="fdca3-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="fdca3-129">Так как каждый метод может иметь свой собственный квалификаторы [IWbemQualifierSet указатель](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающему объекту добавить, изменить или удалить эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="fdca3-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="fdca3-130">Требования</span><span class="sxs-lookup"><span data-stu-id="fdca3-130">Requirements</span></span>

<span data-ttu-id="fdca3-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdca3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="fdca3-132">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fdca3-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="fdca3-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fdca3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fdca3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fdca3-134">See also</span></span>

- [<span data-ttu-id="fdca3-135">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="fdca3-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)