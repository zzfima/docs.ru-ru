---
title: Функция GetMethodOrigin (Справочник по неуправляемым API)
description: Функция GetMethodOrigin определяет класс, в котором объявлен метод.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35e56494d0082db970afce21da8e63a597f0a535
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458154"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="1c881-103">Функция GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="1c881-103">GetMethodOrigin function</span></span>
<span data-ttu-id="1c881-104">Определяет класс, в котором объявлен метод.</span><span class="sxs-lookup"><span data-stu-id="1c881-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1c881-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c881-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="1c881-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c881-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1c881-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="1c881-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1c881-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1c881-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="1c881-109">[in] Имя метода для объекта, владеющего класс которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="1c881-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="1c881-110">[out] Получает имя класса, которому принадлежит метод.</span><span class="sxs-lookup"><span data-stu-id="1c881-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="1c881-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1c881-111">Return value</span></span>

<span data-ttu-id="1c881-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1c881-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1c881-113">Константа</span><span class="sxs-lookup"><span data-stu-id="1c881-113">Constant</span></span>  |<span data-ttu-id="1c881-114">Значение</span><span class="sxs-lookup"><span data-stu-id="1c881-114">Value</span></span>  |<span data-ttu-id="1c881-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1c881-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1c881-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1c881-116">0x80041002</span></span> | <span data-ttu-id="1c881-117">Указанный метод не найден.</span><span class="sxs-lookup"><span data-stu-id="1c881-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1c881-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1c881-118">0x80041008</span></span> | <span data-ttu-id="1c881-119">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="1c881-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1c881-120">0</span><span class="sxs-lookup"><span data-stu-id="1c881-120">0</span></span> | <span data-ttu-id="1c881-121">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="1c881-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1c881-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c881-122">Remarks</span></span>

<span data-ttu-id="1c881-123">Эта функция создает оболочку для вызова [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="1c881-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1c881-124">Поскольку класс может наследовать методы из одного или нескольких базовых классов, разработчики часто требуется определить класс, в котором определен данный метод.</span><span class="sxs-lookup"><span data-stu-id="1c881-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="1c881-125">`pstrClassName` Параметр не должен указывать на допустимый `BSTR` перед вызовом функции, так как это `out` параметр; этот указатель не освобождается после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="1c881-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c881-126">Требования</span><span class="sxs-lookup"><span data-stu-id="1c881-126">Requirements</span></span>  
<span data-ttu-id="1c881-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c881-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c881-128">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1c881-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1c881-129">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1c881-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c881-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1c881-130">See also</span></span>  
[<span data-ttu-id="1c881-131">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="1c881-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
