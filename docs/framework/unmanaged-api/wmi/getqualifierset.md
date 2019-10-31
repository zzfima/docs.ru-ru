---
title: Функция Жеткуалифиерсет (Справочник по неуправляемым API)
description: Функция Жеткуалифиерсет извлекает квалификатор, заданный для класса или экземпляра.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 489e240af3f26e82f2459ac4b4dbd944639f78fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127440"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="27a72-103">Функция Жеткуалифиерсет</span><span class="sxs-lookup"><span data-stu-id="27a72-103">GetQualifierSet function</span></span>
<span data-ttu-id="27a72-104">Получает набор квалификатор для экземпляра или определения класса.</span><span class="sxs-lookup"><span data-stu-id="27a72-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="27a72-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27a72-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="27a72-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="27a72-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="27a72-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="27a72-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="27a72-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="27a72-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="27a72-109">заполняет Получает указатель интерфейса, который разрешает доступ к квалификаторам объекта класса.</span><span class="sxs-lookup"><span data-stu-id="27a72-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="27a72-110">Параметр `ppQualSet` не может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="27a72-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="27a72-111">При возникновении ошибки новый объект не возвращается, и указатель остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="27a72-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="27a72-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27a72-112">Return value</span></span>

<span data-ttu-id="27a72-113">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="27a72-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="27a72-114">Константа</span><span class="sxs-lookup"><span data-stu-id="27a72-114">Constant</span></span>  |<span data-ttu-id="27a72-115">значения</span><span class="sxs-lookup"><span data-stu-id="27a72-115">Value</span></span>  |<span data-ttu-id="27a72-116">Описание</span><span class="sxs-lookup"><span data-stu-id="27a72-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="27a72-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="27a72-117">0x80041001</span></span> | <span data-ttu-id="27a72-118">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="27a72-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="27a72-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="27a72-119">0x80041002</span></span> | <span data-ttu-id="27a72-120">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="27a72-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="27a72-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="27a72-121">0x80041006</span></span> | <span data-ttu-id="27a72-122">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="27a72-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="27a72-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="27a72-123">0x80041008</span></span> | <span data-ttu-id="27a72-124">Параметр — `null`.</span><span class="sxs-lookup"><span data-stu-id="27a72-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="27a72-125">0</span><span class="sxs-lookup"><span data-stu-id="27a72-125">0</span></span> | <span data-ttu-id="27a72-126">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="27a72-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="27a72-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="27a72-127">Remarks</span></span>

<span data-ttu-id="27a72-128">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жеткуалифиерсет](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="27a72-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="27a72-129">[Указатель ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающей стороне добавлять, изменять или удалять эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="27a72-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="27a72-130">Такие добавленные, измененные или удаленные квалификаторы применяются ко всему определению экземпляра или класса.</span><span class="sxs-lookup"><span data-stu-id="27a72-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="27a72-131">Требования</span><span class="sxs-lookup"><span data-stu-id="27a72-131">Requirements</span></span>  
<span data-ttu-id="27a72-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27a72-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27a72-133">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="27a72-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="27a72-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27a72-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a72-135">См. также</span><span class="sxs-lookup"><span data-stu-id="27a72-135">See also</span></span>

- [<span data-ttu-id="27a72-136">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="27a72-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
