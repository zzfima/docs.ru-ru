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
ms.openlocfilehash: d1cc754fcf7d1defa815bb0a74b7c2b4a6909478
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085758"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="75bfe-103">Функция GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="75bfe-103">GetMethodOrigin function</span></span>
<span data-ttu-id="75bfe-104">Определяет класс, в котором объявлен метод.</span><span class="sxs-lookup"><span data-stu-id="75bfe-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="75bfe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75bfe-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="75bfe-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="75bfe-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="75bfe-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="75bfe-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="75bfe-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="75bfe-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="75bfe-109">[in] Имя метода, для которого класс-владелец запрашиваемого объекта.</span><span class="sxs-lookup"><span data-stu-id="75bfe-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="75bfe-110">[out] Получает имя класса, которому принадлежит метод.</span><span class="sxs-lookup"><span data-stu-id="75bfe-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="75bfe-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="75bfe-111">Return value</span></span>

<span data-ttu-id="75bfe-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="75bfe-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="75bfe-113">Константа</span><span class="sxs-lookup"><span data-stu-id="75bfe-113">Constant</span></span>  |<span data-ttu-id="75bfe-114">Значение</span><span class="sxs-lookup"><span data-stu-id="75bfe-114">Value</span></span>  |<span data-ttu-id="75bfe-115">Описание</span><span class="sxs-lookup"><span data-stu-id="75bfe-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="75bfe-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="75bfe-116">0x80041002</span></span> | <span data-ttu-id="75bfe-117">Указанный метод не найден.</span><span class="sxs-lookup"><span data-stu-id="75bfe-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="75bfe-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="75bfe-118">0x80041008</span></span> | <span data-ttu-id="75bfe-119">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="75bfe-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="75bfe-120">0</span><span class="sxs-lookup"><span data-stu-id="75bfe-120">0</span></span> | <span data-ttu-id="75bfe-121">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="75bfe-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="75bfe-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="75bfe-122">Remarks</span></span>

<span data-ttu-id="75bfe-123">Эта функция создает оболочку для вызова [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) метод.</span><span class="sxs-lookup"><span data-stu-id="75bfe-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="75bfe-124">Поскольку класс может наследовать методы из одного или нескольких базовых классов, разработчики часто хотят определить класс, в котором определен данный метод.</span><span class="sxs-lookup"><span data-stu-id="75bfe-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="75bfe-125">`pstrClassName` Параметр не должен указывать на допустимый `BSTR` перед вызовом функции, так как это `out` параметр; этот указатель не освобождается после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="75bfe-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="75bfe-126">Требования</span><span class="sxs-lookup"><span data-stu-id="75bfe-126">Requirements</span></span>  
<span data-ttu-id="75bfe-127">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75bfe-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75bfe-128">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="75bfe-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="75bfe-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="75bfe-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bfe-130">См. также</span><span class="sxs-lookup"><span data-stu-id="75bfe-130">See also</span></span>  
[<span data-ttu-id="75bfe-131">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="75bfe-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
