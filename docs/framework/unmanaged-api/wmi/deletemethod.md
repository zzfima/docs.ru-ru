---
title: Функция DeleteMethod (Неуправляемая ссылка на API)
description: Функция DeleteMethod удаляет указанный метод из определения класса CIM.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4059555d74c0b0f151332ddcf9faedecf238e795
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174996"
---
# <a name="deletemethod-function"></a><span data-ttu-id="41058-103">Функция DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="41058-103">DeleteMethod function</span></span>
<span data-ttu-id="41058-104">Удаляет указанный метод из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="41058-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="41058-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41058-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="41058-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="41058-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="41058-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="41058-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="41058-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="41058-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="41058-109">(в) Название метода для удаления из таблицы класса.</span><span class="sxs-lookup"><span data-stu-id="41058-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="41058-110">`wszName`должны быть указателем на `LPCWSTR`действительный .</span><span class="sxs-lookup"><span data-stu-id="41058-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="41058-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="41058-111">Return value</span></span>

<span data-ttu-id="41058-112">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="41058-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="41058-113">Постоянно</span><span class="sxs-lookup"><span data-stu-id="41058-113">Constant</span></span>  |<span data-ttu-id="41058-114">Значение</span><span class="sxs-lookup"><span data-stu-id="41058-114">Value</span></span>  |<span data-ttu-id="41058-115">Описание</span><span class="sxs-lookup"><span data-stu-id="41058-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="41058-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="41058-116">0x80041002</span></span> | <span data-ttu-id="41058-117">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="41058-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="41058-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="41058-118">0x80041006</span></span> | <span data-ttu-id="41058-119">Недостаточно памяти для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="41058-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="41058-120">0</span><span class="sxs-lookup"><span data-stu-id="41058-120">0</span></span> | <span data-ttu-id="41058-121">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="41058-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="41058-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="41058-122">Remarks</span></span>

<span data-ttu-id="41058-123">Эта функция завершает вызов методом [IWbemClassObject::DeleteMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod)</span><span class="sxs-lookup"><span data-stu-id="41058-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="41058-124">Удаление метода не поддерживается для указателей [IWbemClassObject,](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) которые указывают на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="41058-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="41058-125">Требования</span><span class="sxs-lookup"><span data-stu-id="41058-125">Requirements</span></span>  
 <span data-ttu-id="41058-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41058-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41058-127">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="41058-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="41058-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41058-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41058-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="41058-129">See also</span></span>

- [<span data-ttu-id="41058-130">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="41058-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
