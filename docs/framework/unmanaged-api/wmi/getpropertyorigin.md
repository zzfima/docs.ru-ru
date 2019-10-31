---
title: Функция Жетпропертйоригин (Справочник по неуправляемым API)
description: Функция Жетпропертйоригин определяет класс, в котором объявлено свойство.
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
ms.openlocfilehash: 6cab3765f0359f5dd18831acaaa1aefce3fe1081
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101850"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="a822d-103">Функция GetPropertyOrigin</span><span class="sxs-lookup"><span data-stu-id="a822d-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="a822d-104">Определяет класс, в котором объявлено свойство.</span><span class="sxs-lookup"><span data-stu-id="a822d-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a822d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a822d-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="a822d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a822d-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="a822d-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="a822d-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="a822d-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="a822d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="a822d-109">окне Имя свойства для объекта, класс-владелец которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="a822d-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="a822d-110">заполняет Получает имя класса, владеющего свойством.</span><span class="sxs-lookup"><span data-stu-id="a822d-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="a822d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a822d-111">Return value</span></span>

<span data-ttu-id="a822d-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="a822d-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a822d-113">Константа</span><span class="sxs-lookup"><span data-stu-id="a822d-113">Constant</span></span>  |<span data-ttu-id="a822d-114">значения</span><span class="sxs-lookup"><span data-stu-id="a822d-114">Value</span></span>  |<span data-ttu-id="a822d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a822d-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="a822d-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a822d-116">0x80041001</span></span> | <span data-ttu-id="a822d-117">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="a822d-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a822d-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a822d-118">0x80041002</span></span> | <span data-ttu-id="a822d-119">Указанное свойство не найдено.</span><span class="sxs-lookup"><span data-stu-id="a822d-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a822d-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a822d-120">0x80041008</span></span> | <span data-ttu-id="a822d-121">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="a822d-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a822d-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a822d-122">0x80041006</span></span> | <span data-ttu-id="a822d-123">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="a822d-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a822d-124">0</span><span class="sxs-lookup"><span data-stu-id="a822d-124">0</span></span> | <span data-ttu-id="a822d-125">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a822d-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="a822d-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="a822d-126">Remarks</span></span>

<span data-ttu-id="a822d-127">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетпропертйоригин](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) .</span><span class="sxs-lookup"><span data-stu-id="a822d-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="a822d-128">Поскольку класс может наследовать свойства от одного или нескольких базовых классов, разработчики часто хотят определить свойство, в котором определен определенный метод.</span><span class="sxs-lookup"><span data-stu-id="a822d-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="a822d-129">Перед вызовом функции параметр `pstrClassName` не должен указывать на допустимый `BSTR`, так как это параметр `out`; Этот указатель не освобождается после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="a822d-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="a822d-130">Требования</span><span class="sxs-lookup"><span data-stu-id="a822d-130">Requirements</span></span>

<span data-ttu-id="a822d-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a822d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a822d-132">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="a822d-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="a822d-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a822d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a822d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a822d-134">See also</span></span>

- [<span data-ttu-id="a822d-135">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="a822d-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
