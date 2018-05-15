---
title: Функция GetPropertyOrigin (Справочник по API Unmnaged)
description: Функция GetPropertyOrigin определяет класс, в котором объявлено свойство.
ms.date: 11/06/2017
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
ms.openlocfilehash: f16bc5ce23e6bf110a140d10f0e787935070dbcc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="8084b-103">Функция GetPropertyOrigin</span><span class="sxs-lookup"><span data-stu-id="8084b-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="8084b-104">Определяет класс, в котором объявлено свойство.</span><span class="sxs-lookup"><span data-stu-id="8084b-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8084b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8084b-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="8084b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8084b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8084b-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="8084b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8084b-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8084b-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="8084b-109">[in] Имя свойства для объекта, владеющего класс которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="8084b-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="8084b-110">[out] Получает имя класса, которому принадлежит свойство.</span><span class="sxs-lookup"><span data-stu-id="8084b-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="8084b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8084b-111">Return value</span></span>

<span data-ttu-id="8084b-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="8084b-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8084b-113">Константа</span><span class="sxs-lookup"><span data-stu-id="8084b-113">Constant</span></span>  |<span data-ttu-id="8084b-114">Значение</span><span class="sxs-lookup"><span data-stu-id="8084b-114">Value</span></span>  |<span data-ttu-id="8084b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8084b-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="8084b-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8084b-116">0x80041001</span></span> | <span data-ttu-id="8084b-117">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="8084b-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="8084b-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8084b-118">0x80041002</span></span> | <span data-ttu-id="8084b-119">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="8084b-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8084b-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8084b-120">0x80041008</span></span> | <span data-ttu-id="8084b-121">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="8084b-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8084b-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8084b-122">0x80041006</span></span> | <span data-ttu-id="8084b-123">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="8084b-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8084b-124">0</span><span class="sxs-lookup"><span data-stu-id="8084b-124">0</span></span> | <span data-ttu-id="8084b-125">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="8084b-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8084b-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="8084b-126">Remarks</span></span>

<span data-ttu-id="8084b-127">Эта функция создает оболочку для вызова [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="8084b-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="8084b-128">Поскольку класс может наследовать свойства из одного или нескольких базовых классов, разработчики часто требуется определить свойства, в котором определен данный метод.</span><span class="sxs-lookup"><span data-stu-id="8084b-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="8084b-129">`pstrClassName` Параметр не должен указывать на допустимый `BSTR` перед вызовом функции, так как это `out` параметр; этот указатель не освобождается после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="8084b-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="8084b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="8084b-130">Requirements</span></span>  
<span data-ttu-id="8084b-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8084b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8084b-132">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8084b-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8084b-133">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8084b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8084b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8084b-134">See also</span></span>  
[<span data-ttu-id="8084b-135">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="8084b-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
