---
title: Функция Delete (Справочник по неуправляемым API)
description: Функция Delete удаляет указанное свойство и все его квалификаторы из определения класса CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6b8f287be831702dd31a8335f9b2f6447bcee540
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127668"
---
# <a name="delete-function"></a><span data-ttu-id="23456-103">Функция Delete</span><span class="sxs-lookup"><span data-stu-id="23456-103">Delete function</span></span>

<span data-ttu-id="23456-104">Удаляет указанное свойство и все его квалификаторы из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="23456-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="23456-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23456-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="23456-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="23456-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="23456-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="23456-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="23456-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="23456-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="23456-109">окне Имя удаляемого свойства.</span><span class="sxs-lookup"><span data-stu-id="23456-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="23456-110">`wszName` должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="23456-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="23456-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="23456-111">Return value</span></span>

<span data-ttu-id="23456-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="23456-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="23456-113">Константа</span><span class="sxs-lookup"><span data-stu-id="23456-113">Constant</span></span>  |<span data-ttu-id="23456-114">значения</span><span class="sxs-lookup"><span data-stu-id="23456-114">Value</span></span>  |<span data-ttu-id="23456-115">Описание</span><span class="sxs-lookup"><span data-stu-id="23456-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="23456-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="23456-116">0x80041001</span></span> | <span data-ttu-id="23456-117">Произошла неопределенная ошибка.</span><span class="sxs-lookup"><span data-stu-id="23456-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="23456-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="23456-118">0x80041016</span></span> | <span data-ttu-id="23456-119">Свойство не может быть удалено.</span><span class="sxs-lookup"><span data-stu-id="23456-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="23456-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="23456-120">0x80041008</span></span> | <span data-ttu-id="23456-121">`wszName` недопустим.</span><span class="sxs-lookup"><span data-stu-id="23456-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="23456-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="23456-122">0x80041002</span></span> | <span data-ttu-id="23456-123">Указанное свойство не существует.</span><span class="sxs-lookup"><span data-stu-id="23456-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="23456-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="23456-124">0x80041006</span></span> | <span data-ttu-id="23456-125">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="23456-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="23456-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="23456-126">0x8004101c</span></span> | <span data-ttu-id="23456-127">Свойство наследуется от базового класса.</span><span class="sxs-lookup"><span data-stu-id="23456-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="23456-128">Свойство является системным свойством.</span><span class="sxs-lookup"><span data-stu-id="23456-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="23456-129">0</span><span class="sxs-lookup"><span data-stu-id="23456-129">0</span></span> | <span data-ttu-id="23456-130">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="23456-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="23456-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="23456-131">0x80041030</span></span> | <span data-ttu-id="23456-132">Функция удалила значение переопределения по умолчанию для текущего класса.</span><span class="sxs-lookup"><span data-stu-id="23456-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="23456-133">Значение по умолчанию для этого свойства в родительском классе было повторно активировано.</span><span class="sxs-lookup"><span data-stu-id="23456-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="23456-134">Заметки</span><span class="sxs-lookup"><span data-stu-id="23456-134">Remarks</span></span>

<span data-ttu-id="23456-135">Эта функция создает оболочку для вызова метода [ивбемклассобжект::D удалить](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) .</span><span class="sxs-lookup"><span data-stu-id="23456-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="23456-136">Требования</span><span class="sxs-lookup"><span data-stu-id="23456-136">Requirements</span></span>

<span data-ttu-id="23456-137">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23456-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="23456-138">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="23456-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="23456-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="23456-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="23456-140">См. также</span><span class="sxs-lookup"><span data-stu-id="23456-140">See also</span></span>

- [<span data-ttu-id="23456-141">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="23456-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
