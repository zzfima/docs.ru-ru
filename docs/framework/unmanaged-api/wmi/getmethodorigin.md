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
ms.openlocfilehash: 193caa894b8697a65e8821c01a63dde9cc5b5ccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153716"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="5dc4d-103">Функция GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="5dc4d-103">GetMethodOrigin function</span></span>
<span data-ttu-id="5dc4d-104">Определяет класс, в котором объявлен метод.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5dc4d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5dc4d-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="5dc4d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5dc4d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5dc4d-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5dc4d-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="5dc4d-109">[in] Имя метода, для которого класс-владелец запрашиваемого объекта.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="5dc4d-110">[out] Получает имя класса, которому принадлежит метод.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="5dc4d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5dc4d-111">Return value</span></span>

<span data-ttu-id="5dc4d-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5dc4d-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5dc4d-113">Константа</span><span class="sxs-lookup"><span data-stu-id="5dc4d-113">Constant</span></span>  |<span data-ttu-id="5dc4d-114">Значение</span><span class="sxs-lookup"><span data-stu-id="5dc4d-114">Value</span></span>  |<span data-ttu-id="5dc4d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5dc4d-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="5dc4d-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5dc4d-116">0x80041002</span></span> | <span data-ttu-id="5dc4d-117">Указанный метод не найден.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5dc4d-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5dc4d-118">0x80041008</span></span> | <span data-ttu-id="5dc4d-119">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5dc4d-120">0</span><span class="sxs-lookup"><span data-stu-id="5dc4d-120">0</span></span> | <span data-ttu-id="5dc4d-121">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5dc4d-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="5dc4d-122">Remarks</span></span>

<span data-ttu-id="5dc4d-123">Эта функция создает оболочку для вызова [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="5dc4d-124">Поскольку класс может наследовать методы из одного или нескольких базовых классов, разработчики часто хотят определить класс, в котором определен данный метод.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="5dc4d-125">`pstrClassName` Параметр не должен указывать на допустимый `BSTR` перед вызовом функции, так как это `out` параметр; этот указатель не освобождается после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="5dc4d-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="5dc4d-126">Требования</span><span class="sxs-lookup"><span data-stu-id="5dc4d-126">Requirements</span></span>  
<span data-ttu-id="5dc4d-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc4d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc4d-128">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5dc4d-128">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="5dc4d-129">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5dc4d-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5dc4d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="5dc4d-130">See also</span></span>

- [<span data-ttu-id="5dc4d-131">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5dc4d-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
