---
title: Функция Жетмесодкуалифиерсет (Справочник по неуправляемым API)
description: Функция Жетмесодкуалифиерсет извлекает набор квалификаторов метода.
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
ms.openlocfilehash: 86a7788736c3c12cfcfd405de88dfadfb14c1eca
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798532"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="a071c-103">Функция GetMethodQualifierSet</span><span class="sxs-lookup"><span data-stu-id="a071c-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="a071c-104">Получает набор квалификаторов для определенного метода.</span><span class="sxs-lookup"><span data-stu-id="a071c-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a071c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a071c-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="a071c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a071c-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="a071c-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="a071c-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="a071c-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="a071c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="a071c-109">окне Имя метода.</span><span class="sxs-lookup"><span data-stu-id="a071c-109">[in] The method  name.</span></span> <span data-ttu-id="a071c-110">`wszMethod`должен указывать на допустимое `LPCWSTR`значение.</span><span class="sxs-lookup"><span data-stu-id="a071c-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="a071c-111">заполняет Получает указатель интерфейса, который разрешает доступ к квалификаторам метода.</span><span class="sxs-lookup"><span data-stu-id="a071c-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="a071c-112">Параметр `ppQualSet` не может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a071c-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="a071c-113">При возникновении ошибки новый объект не возвращается, и указатель устанавливается на точку `null`.</span><span class="sxs-lookup"><span data-stu-id="a071c-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a071c-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a071c-114">Return value</span></span>

<span data-ttu-id="a071c-115">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="a071c-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a071c-116">Константа</span><span class="sxs-lookup"><span data-stu-id="a071c-116">Constant</span></span>  |<span data-ttu-id="a071c-117">Значение</span><span class="sxs-lookup"><span data-stu-id="a071c-117">Value</span></span>  |<span data-ttu-id="a071c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a071c-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a071c-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a071c-119">0x80041002</span></span> | <span data-ttu-id="a071c-120">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="a071c-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a071c-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a071c-121">0x80041008</span></span> | <span data-ttu-id="a071c-122">Параметр имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a071c-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a071c-123">0</span><span class="sxs-lookup"><span data-stu-id="a071c-123">0</span></span> | <span data-ttu-id="a071c-124">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a071c-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="a071c-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="a071c-125">Remarks</span></span>

<span data-ttu-id="a071c-126">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетмесодкуалифиерсет](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="a071c-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="a071c-127">Вызов этой функции поддерживается только в том случае, если текущий объект является определением класса CIM.</span><span class="sxs-lookup"><span data-stu-id="a071c-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="a071c-128">Управление методами недоступно для [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="a071c-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="a071c-129">Поскольку каждый метод может иметь собственные квалификаторы, [указатель ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающей стороне добавить, изменить или удалить эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="a071c-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="a071c-130">Требования</span><span class="sxs-lookup"><span data-stu-id="a071c-130">Requirements</span></span>

<span data-ttu-id="a071c-131">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a071c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a071c-132">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="a071c-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="a071c-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a071c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a071c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a071c-134">See also</span></span>

- [<span data-ttu-id="a071c-135">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="a071c-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
