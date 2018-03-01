---
title: "Функция GetPropertyOrigin (Справочник по API Unmnaged)"
description: "Функция GetPropertyOrigin определяет класс, в котором объявлено свойство."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0a79bfc62ad776cb2bfab2c143d19761d64358bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="c96b1-103">Функция GetPropertyOrigin</span><span class="sxs-lookup"><span data-stu-id="c96b1-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="c96b1-104">Определяет класс, в котором объявлено свойство.</span><span class="sxs-lookup"><span data-stu-id="c96b1-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c96b1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c96b1-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="c96b1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c96b1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c96b1-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="c96b1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c96b1-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c96b1-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="c96b1-109">[in] Имя свойства для объекта, владеющего класс которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="c96b1-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="c96b1-110">[out] Получает имя класса, которому принадлежит свойство.</span><span class="sxs-lookup"><span data-stu-id="c96b1-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="c96b1-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c96b1-111">Return value</span></span>

<span data-ttu-id="c96b1-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="c96b1-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c96b1-113">Константа</span><span class="sxs-lookup"><span data-stu-id="c96b1-113">Constant</span></span>  |<span data-ttu-id="c96b1-114">Значение</span><span class="sxs-lookup"><span data-stu-id="c96b1-114">Value</span></span>  |<span data-ttu-id="c96b1-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="c96b1-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="c96b1-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c96b1-116">0x80041001</span></span> | <span data-ttu-id="c96b1-117">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="c96b1-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c96b1-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c96b1-118">0x80041002</span></span> | <span data-ttu-id="c96b1-119">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="c96b1-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c96b1-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c96b1-120">0x80041008</span></span> | <span data-ttu-id="c96b1-121">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="c96b1-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c96b1-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c96b1-122">0x80041006</span></span> | <span data-ttu-id="c96b1-123">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="c96b1-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c96b1-124">0</span><span class="sxs-lookup"><span data-stu-id="c96b1-124">0</span></span> | <span data-ttu-id="c96b1-125">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="c96b1-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c96b1-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="c96b1-126">Remarks</span></span>

<span data-ttu-id="c96b1-127">Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="c96b1-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="c96b1-128">Поскольку класс может наследовать свойства из одного или нескольких базовых классов, разработчики часто требуется определить свойства, в котором определен данный метод.</span><span class="sxs-lookup"><span data-stu-id="c96b1-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="c96b1-129">`pstrClassName` Параметр не должен указывать на допустимый `BSTR` перед вызовом функции, так как это `out` параметр; этот указатель не освобождается после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="c96b1-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="c96b1-130">Требования</span><span class="sxs-lookup"><span data-stu-id="c96b1-130">Requirements</span></span>  
<span data-ttu-id="c96b1-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c96b1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c96b1-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c96b1-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c96b1-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c96b1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96b1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="c96b1-134">See also</span></span>  
[<span data-ttu-id="c96b1-135">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="c96b1-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
