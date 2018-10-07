---
title: Функция GetPropertyHandle (Справочник по неуправляемым API)
description: Функция GetPropertyHandle возвращает уникальный дескриптор этого свойства удостоверения.
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
ms.openlocfilehash: 94171b0708c97eb7510e916e451ed03645d706f3
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837444"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="05163-103">Функция GetPropertyHandle</span><span class="sxs-lookup"><span data-stu-id="05163-103">GetPropertyHandle function</span></span>
<span data-ttu-id="05163-104">Возвращает уникальный маркер, определяющий свойство.</span><span class="sxs-lookup"><span data-stu-id="05163-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="05163-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05163-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="05163-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="05163-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="05163-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="05163-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="05163-108">[in] Указатель на [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="05163-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="05163-109">[in] Завершающаяся нулем строка кодировке UTF16 знака, содержащее имя свойства.</span><span class="sxs-lookup"><span data-stu-id="05163-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="05163-110">[out] Указатель на [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) член перечисления, представляющее тип CIM данного свойства.</span><span class="sxs-lookup"><span data-stu-id="05163-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="05163-111">[out] Указатель на целое число, которое содержит дескриптор свойства.</span><span class="sxs-lookup"><span data-stu-id="05163-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="05163-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="05163-112">Return value</span></span>

<span data-ttu-id="05163-113">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="05163-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="05163-114">Константа</span><span class="sxs-lookup"><span data-stu-id="05163-114">Constant</span></span>  |<span data-ttu-id="05163-115">Значение</span><span class="sxs-lookup"><span data-stu-id="05163-115">Value</span></span>  |<span data-ttu-id="05163-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="05163-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="05163-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="05163-117">0x80041002</span></span> | <span data-ttu-id="05163-118">Свойство с указанным именем не найден.</span><span class="sxs-lookup"><span data-stu-id="05163-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="05163-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="05163-119">0x80041008</span></span> | <span data-ttu-id="05163-120">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="05163-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="05163-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="05163-121">0x8004100c</span></span> | <span data-ttu-id="05163-122">Запрошенное свойство имеет тип, `CIM_OBJECT` или `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="05163-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="05163-123">0</span><span class="sxs-lookup"><span data-stu-id="05163-123">0</span></span> | <span data-ttu-id="05163-124">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="05163-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="05163-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="05163-125">Remarks</span></span>

<span data-ttu-id="05163-126">Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) метод.</span><span class="sxs-lookup"><span data-stu-id="05163-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="05163-127">Вы можете использовать этот дескриптор для идентификации свойств, при использовании [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) методы для чтения или записи значения свойств.</span><span class="sxs-lookup"><span data-stu-id="05163-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="05163-128">Дескрипторы может быть извлечен для свойства всех типов данных, отличных от `CIM_OBJECT` и `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="05163-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="05163-129">Возвращаемые дескрипторы работы для всех экземпляров класса.</span><span class="sxs-lookup"><span data-stu-id="05163-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="05163-130">Требования</span><span class="sxs-lookup"><span data-stu-id="05163-130">Requirements</span></span>  
<span data-ttu-id="05163-131">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05163-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05163-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="05163-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="05163-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="05163-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05163-134">См. также</span><span class="sxs-lookup"><span data-stu-id="05163-134">See also</span></span>  
[<span data-ttu-id="05163-135">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="05163-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
