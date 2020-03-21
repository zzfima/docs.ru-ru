---
title: Функция GetMethodOrigin (Неуправляемая справка API)
description: Функция GetMethodOrigin определяет класс, в котором объявляется метод.
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
ms.openlocfilehash: 5b4609b6649be875aea7dfcf52ba36b1e98ab7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176803"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="ddf91-103">Функция GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="ddf91-103">GetMethodOrigin function</span></span>
<span data-ttu-id="ddf91-104">Определяет класс, в котором объявлен метод.</span><span class="sxs-lookup"><span data-stu-id="ddf91-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ddf91-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddf91-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a><span data-ttu-id="ddf91-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ddf91-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ddf91-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="ddf91-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ddf91-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="ddf91-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="ddf91-109">(в) Имя метода для объекта, владеющий классом.</span><span class="sxs-lookup"><span data-stu-id="ddf91-109">[in] The name of the method for the object whose owning class is being requested.</span></span>

`pstrClassName`  
<span data-ttu-id="ddf91-110">(ваут) Получает название класса, которому принадлежит метод.</span><span class="sxs-lookup"><span data-stu-id="ddf91-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="ddf91-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ddf91-111">Return value</span></span>

<span data-ttu-id="ddf91-112">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ddf91-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ddf91-113">Постоянно</span><span class="sxs-lookup"><span data-stu-id="ddf91-113">Constant</span></span>  |<span data-ttu-id="ddf91-114">Значение</span><span class="sxs-lookup"><span data-stu-id="ddf91-114">Value</span></span>  |<span data-ttu-id="ddf91-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ddf91-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ddf91-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ddf91-116">0x80041002</span></span> | <span data-ttu-id="ddf91-117">Указанный метод не найден.</span><span class="sxs-lookup"><span data-stu-id="ddf91-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ddf91-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ddf91-118">0x80041008</span></span> | <span data-ttu-id="ddf91-119">Один или несколько параметров недействительны.</span><span class="sxs-lookup"><span data-stu-id="ddf91-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ddf91-120">0</span><span class="sxs-lookup"><span data-stu-id="ddf91-120">0</span></span> | <span data-ttu-id="ddf91-121">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="ddf91-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ddf91-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="ddf91-122">Remarks</span></span>

<span data-ttu-id="ddf91-123">Эта функция завершает вызов методом [IWbemClassObject::GetMethodOrigin.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)</span><span class="sxs-lookup"><span data-stu-id="ddf91-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="ddf91-124">Поскольку класс может наследовать методы из одного или нескольких базовых классов, разработчики часто хотят определить класс, в котором определен данный метод.</span><span class="sxs-lookup"><span data-stu-id="ddf91-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="ddf91-125">Параметр `pstrClassName` не должен указывать на допустимый `BSTR` перед `out` вызовом функции, поскольку это параметр; этот указатель не разбирается после возврата функции.</span><span class="sxs-lookup"><span data-stu-id="ddf91-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="ddf91-126">Требования</span><span class="sxs-lookup"><span data-stu-id="ddf91-126">Requirements</span></span>  
<span data-ttu-id="ddf91-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddf91-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddf91-128">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ddf91-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ddf91-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ddf91-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf91-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ddf91-130">See also</span></span>

- [<span data-ttu-id="ddf91-131">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="ddf91-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
