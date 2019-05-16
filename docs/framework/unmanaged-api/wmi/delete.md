---
title: Удалить функцию (Справочник по неуправляемым API)
description: Функция удаления удаляет указанное свойство и все его квалификаторы из определения класса CIM.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 965143eadd6e2dde498d5ee73e4f9e8bfded8a6e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636724"
---
# <a name="delete-function"></a><span data-ttu-id="ac9fe-103">Функция Delete</span><span class="sxs-lookup"><span data-stu-id="ac9fe-103">Delete function</span></span>

<span data-ttu-id="ac9fe-104">Удаляет указанное свойство и все его квалификаторы из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ac9fe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac9fe-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="ac9fe-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac9fe-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ac9fe-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ac9fe-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="ac9fe-109">[in] Имя свойства для удаления.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="ac9fe-110">`wszName` должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ac9fe-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac9fe-111">Return value</span></span>

<span data-ttu-id="ac9fe-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ac9fe-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ac9fe-113">Константа</span><span class="sxs-lookup"><span data-stu-id="ac9fe-113">Constant</span></span>  |<span data-ttu-id="ac9fe-114">Значение</span><span class="sxs-lookup"><span data-stu-id="ac9fe-114">Value</span></span>  |<span data-ttu-id="ac9fe-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ac9fe-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ac9fe-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ac9fe-116">0x80041001</span></span> | <span data-ttu-id="ac9fe-117">Произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="ac9fe-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="ac9fe-118">0x80041016</span></span> | <span data-ttu-id="ac9fe-119">Не удается удалить свойство.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ac9fe-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ac9fe-120">0x80041008</span></span> | <span data-ttu-id="ac9fe-121">`wszName` недопустим.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="ac9fe-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ac9fe-122">0x80041002</span></span> | <span data-ttu-id="ac9fe-123">Указанное свойство не существует.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ac9fe-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ac9fe-124">0x80041006</span></span> | <span data-ttu-id="ac9fe-125">Не хватает памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="ac9fe-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="ac9fe-126">0x8004101c</span></span> | <span data-ttu-id="ac9fe-127">Свойство наследуется от базового класса.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="ac9fe-128">Свойство является страницей системных свойств.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ac9fe-129">0</span><span class="sxs-lookup"><span data-stu-id="ac9fe-129">0</span></span> | <span data-ttu-id="ac9fe-130">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="ac9fe-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="ac9fe-131">0x80041030</span></span> | <span data-ttu-id="ac9fe-132">Функция удалить значение override по умолчанию для текущего класса.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="ac9fe-133">Значение по умолчанию для этого свойства в родительском классе-родителе возобновлено.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ac9fe-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac9fe-134">Remarks</span></span>

<span data-ttu-id="ac9fe-135">Эта функция создает оболочку для вызова [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) метод.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac9fe-136">Требования</span><span class="sxs-lookup"><span data-stu-id="ac9fe-136">Requirements</span></span>

<span data-ttu-id="ac9fe-137">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac9fe-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ac9fe-138">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ac9fe-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ac9fe-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9fe-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ac9fe-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ac9fe-140">See also</span></span>

- [<span data-ttu-id="ac9fe-141">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="ac9fe-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
