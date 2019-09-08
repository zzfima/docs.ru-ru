---
title: Функция Жетпропертихандле (Справочник по неуправляемым API)
description: Функция Жетпропертихандле Возвращает уникальный маркер, идентифицирующий свойство.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d72b0da43971a74a08a249b19dfc0d446eeb5e6a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798544"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="18acd-103">Функция GetPropertyHandle</span><span class="sxs-lookup"><span data-stu-id="18acd-103">GetPropertyHandle function</span></span>

<span data-ttu-id="18acd-104">Возвращает уникальный маркер, определяющий свойство.</span><span class="sxs-lookup"><span data-stu-id="18acd-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="18acd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18acd-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="18acd-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="18acd-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="18acd-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="18acd-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="18acd-108">окне Указатель на экземпляр [ивбемобжектакцесс](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .</span><span class="sxs-lookup"><span data-stu-id="18acd-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="18acd-109">окне Строка символов в кодировке UTF16, заканчивающаяся нулем и содержащая имя свойства.</span><span class="sxs-lookup"><span data-stu-id="18acd-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="18acd-110">заполняет Указатель на [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) член перечисления, представляющий CIM-тип свойства.</span><span class="sxs-lookup"><span data-stu-id="18acd-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="18acd-111">заполняет Указатель на целое число, содержащее маркер свойства.</span><span class="sxs-lookup"><span data-stu-id="18acd-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="18acd-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="18acd-112">Return value</span></span>

<span data-ttu-id="18acd-113">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="18acd-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="18acd-114">Константа</span><span class="sxs-lookup"><span data-stu-id="18acd-114">Constant</span></span>  |<span data-ttu-id="18acd-115">Значение</span><span class="sxs-lookup"><span data-stu-id="18acd-115">Value</span></span>  |<span data-ttu-id="18acd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="18acd-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="18acd-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="18acd-117">0x80041002</span></span> | <span data-ttu-id="18acd-118">Указанное имя свойства не найдено.</span><span class="sxs-lookup"><span data-stu-id="18acd-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="18acd-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="18acd-119">0x80041008</span></span> | <span data-ttu-id="18acd-120">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="18acd-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="18acd-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="18acd-121">0x8004100c</span></span> | <span data-ttu-id="18acd-122">Запрошенное свойство имеет тип `CIM_OBJECT` или. `CIM_ARRAY`</span><span class="sxs-lookup"><span data-stu-id="18acd-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="18acd-123">0</span><span class="sxs-lookup"><span data-stu-id="18acd-123">0</span></span> | <span data-ttu-id="18acd-124">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="18acd-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="18acd-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="18acd-125">Remarks</span></span>

<span data-ttu-id="18acd-126">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетпропертихандле](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) .</span><span class="sxs-lookup"><span data-stu-id="18acd-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="18acd-127">Этот обработчик можно использовать для обнаружения свойств при использовании методов [ивбемобжектакцесс](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) для чтения или записи значений свойств.</span><span class="sxs-lookup"><span data-stu-id="18acd-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="18acd-128">Дескрипторы могут быть получены для свойств всех типов `CIM_OBJECT` данных, кроме и. `CIM_ARRAY`</span><span class="sxs-lookup"><span data-stu-id="18acd-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="18acd-129">Возвращаемые дескрипторы работают для всех экземпляров класса.</span><span class="sxs-lookup"><span data-stu-id="18acd-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="18acd-130">Требования</span><span class="sxs-lookup"><span data-stu-id="18acd-130">Requirements</span></span>

<span data-ttu-id="18acd-131">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18acd-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="18acd-132">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="18acd-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="18acd-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18acd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="18acd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="18acd-134">See also</span></span>

- [<span data-ttu-id="18acd-135">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="18acd-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
