---
title: Функция Жетмесодоригин (Справочник по неуправляемым API)
description: Функция Жетмесодоригин определяет класс, в котором объявлен метод.
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
ms.openlocfilehash: 1f669d5721a7bd9434f0ce4b1e2290c0633e1b46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102534"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="6d8f7-103">Функция GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="6d8f7-103">GetMethodOrigin function</span></span>
<span data-ttu-id="6d8f7-104">Определяет класс, в котором объявлен метод.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="6d8f7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d8f7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="6d8f7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d8f7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6d8f7-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6d8f7-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="6d8f7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="6d8f7-109">окне Имя метода для объекта, класс-владелец которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="6d8f7-110">заполняет Получает имя класса, владеющего методом.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="6d8f7-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6d8f7-111">Return value</span></span>

<span data-ttu-id="6d8f7-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="6d8f7-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6d8f7-113">Константа</span><span class="sxs-lookup"><span data-stu-id="6d8f7-113">Constant</span></span>  |<span data-ttu-id="6d8f7-114">значения</span><span class="sxs-lookup"><span data-stu-id="6d8f7-114">Value</span></span>  |<span data-ttu-id="6d8f7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6d8f7-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="6d8f7-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="6d8f7-116">0x80041002</span></span> | <span data-ttu-id="6d8f7-117">Указанный метод не найден.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6d8f7-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6d8f7-118">0x80041008</span></span> | <span data-ttu-id="6d8f7-119">Один или несколько параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6d8f7-120">0</span><span class="sxs-lookup"><span data-stu-id="6d8f7-120">0</span></span> | <span data-ttu-id="6d8f7-121">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6d8f7-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="6d8f7-122">Remarks</span></span>

<span data-ttu-id="6d8f7-123">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетмесодоригин](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .</span><span class="sxs-lookup"><span data-stu-id="6d8f7-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="6d8f7-124">Поскольку класс может наследовать методы от одного или нескольких базовых классов, разработчики часто хотят определить класс, в котором определен определенный метод.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="6d8f7-125">Перед вызовом функции параметр `pstrClassName` не должен указывать на допустимый `BSTR`, так как это параметр `out`; Этот указатель не освобождается после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="6d8f7-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d8f7-126">Требования</span><span class="sxs-lookup"><span data-stu-id="6d8f7-126">Requirements</span></span>  
<span data-ttu-id="6d8f7-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d8f7-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d8f7-128">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="6d8f7-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6d8f7-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6d8f7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d8f7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="6d8f7-130">See also</span></span>

- [<span data-ttu-id="6d8f7-131">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="6d8f7-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
