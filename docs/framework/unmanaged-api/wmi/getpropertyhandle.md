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
ms.openlocfilehash: d6dc2792b572aae30e9989c81967b86f340d7b83
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038262"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="34169-103">Функция GetPropertyHandle</span><span class="sxs-lookup"><span data-stu-id="34169-103">GetPropertyHandle function</span></span>

<span data-ttu-id="34169-104">Возвращает уникальный маркер, определяющий свойство.</span><span class="sxs-lookup"><span data-stu-id="34169-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="34169-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34169-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="34169-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="34169-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="34169-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="34169-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="34169-108">окне Указатель на экземпляр [ивбемобжектакцесс](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .</span><span class="sxs-lookup"><span data-stu-id="34169-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="34169-109">окне Строка символов в кодировке UTF16, заканчивающаяся нулем и содержащая имя свойства.</span><span class="sxs-lookup"><span data-stu-id="34169-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="34169-110">заполняет Указатель на [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) член перечисления, представляющий CIM-тип свойства.</span><span class="sxs-lookup"><span data-stu-id="34169-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="34169-111">заполняет Указатель на целое число, содержащее маркер свойства.</span><span class="sxs-lookup"><span data-stu-id="34169-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="34169-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="34169-112">Return value</span></span>

<span data-ttu-id="34169-113">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="34169-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="34169-114">Константа</span><span class="sxs-lookup"><span data-stu-id="34169-114">Constant</span></span>  |<span data-ttu-id="34169-115">Значение</span><span class="sxs-lookup"><span data-stu-id="34169-115">Value</span></span>  |<span data-ttu-id="34169-116">Описание</span><span class="sxs-lookup"><span data-stu-id="34169-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="34169-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="34169-117">0x80041002</span></span> | <span data-ttu-id="34169-118">Указанное имя свойства не найдено.</span><span class="sxs-lookup"><span data-stu-id="34169-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="34169-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="34169-119">0x80041008</span></span> | <span data-ttu-id="34169-120">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="34169-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="34169-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="34169-121">0x8004100c</span></span> | <span data-ttu-id="34169-122">Запрошенное свойство имеет тип `CIM_OBJECT` или. `CIM_ARRAY`</span><span class="sxs-lookup"><span data-stu-id="34169-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="34169-123">0</span><span class="sxs-lookup"><span data-stu-id="34169-123">0</span></span> | <span data-ttu-id="34169-124">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="34169-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="34169-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="34169-125">Remarks</span></span>

<span data-ttu-id="34169-126">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетпропертихандле](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) .</span><span class="sxs-lookup"><span data-stu-id="34169-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="34169-127">Этот обработчик можно использовать для обнаружения свойств при использовании методов [ивбемобжектакцесс](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) для чтения или записи значений свойств.</span><span class="sxs-lookup"><span data-stu-id="34169-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="34169-128">Дескрипторы могут быть получены для свойств всех типов `CIM_OBJECT` данных, кроме и. `CIM_ARRAY`</span><span class="sxs-lookup"><span data-stu-id="34169-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="34169-129">Возвращаемые дескрипторы работают для всех экземпляров класса.</span><span class="sxs-lookup"><span data-stu-id="34169-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="34169-130">Требования</span><span class="sxs-lookup"><span data-stu-id="34169-130">Requirements</span></span>

<span data-ttu-id="34169-131">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34169-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="34169-132">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="34169-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="34169-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34169-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="34169-134">См. также</span><span class="sxs-lookup"><span data-stu-id="34169-134">See also</span></span>

- [<span data-ttu-id="34169-135">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="34169-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
