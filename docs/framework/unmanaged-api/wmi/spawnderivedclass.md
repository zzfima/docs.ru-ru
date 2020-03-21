---
title: Функция SpawnDerivedClass (Неуправляемая справка API)
description: Функция SpawnDerivedClass создает новый объект, который происходит от объекта.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174853"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="628ea-103">Функция SpawnDerivedClass</span><span class="sxs-lookup"><span data-stu-id="628ea-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="628ea-104">Создает объект производного класса из указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="628ea-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="628ea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="628ea-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="628ea-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="628ea-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="628ea-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="628ea-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="628ea-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="628ea-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="628ea-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="628ea-109">[in] Reserved.</span></span> <span data-ttu-id="628ea-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="628ea-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="628ea-111">(ваут) Получает указатель на новый объект определения класса.</span><span class="sxs-lookup"><span data-stu-id="628ea-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="628ea-112">При возникновении ошибки новый объект `ppNewClass` не возвращается и остается неизмененным.</span><span class="sxs-lookup"><span data-stu-id="628ea-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="628ea-113">Его ценность `null`не может быть .</span><span class="sxs-lookup"><span data-stu-id="628ea-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="628ea-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="628ea-114">Return value</span></span>

<span data-ttu-id="628ea-115">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="628ea-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="628ea-116">Постоянно</span><span class="sxs-lookup"><span data-stu-id="628ea-116">Constant</span></span>  |<span data-ttu-id="628ea-117">Значение</span><span class="sxs-lookup"><span data-stu-id="628ea-117">Value</span></span>  |<span data-ttu-id="628ea-118">Описание</span><span class="sxs-lookup"><span data-stu-id="628ea-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="628ea-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="628ea-119">0x80041001</span></span> | <span data-ttu-id="628ea-120">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="628ea-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="628ea-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="628ea-121">0x80041016</span></span> | <span data-ttu-id="628ea-122">Была запрошена недействительная операция, например, нерест класса из экземпляра.</span><span class="sxs-lookup"><span data-stu-id="628ea-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="628ea-123">Класс исходного кода не был полностью определен или зарегистрирован в Windows Management, поэтому новый класс производных не допускается.</span><span class="sxs-lookup"><span data-stu-id="628ea-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="628ea-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="628ea-124">0x80041006</span></span> | <span data-ttu-id="628ea-125">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="628ea-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="628ea-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="628ea-126">0x80041008</span></span> | <span data-ttu-id="628ea-127">Параметр `ppNewClass` равен `null`.</span><span class="sxs-lookup"><span data-stu-id="628ea-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="628ea-128">0</span><span class="sxs-lookup"><span data-stu-id="628ea-128">0</span></span> | <span data-ttu-id="628ea-129">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="628ea-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="628ea-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="628ea-130">Remarks</span></span>

<span data-ttu-id="628ea-131">Эта функция завершает вызов методом [IWbemClassObject::SpawnDerivedClass.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)</span><span class="sxs-lookup"><span data-stu-id="628ea-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="628ea-132">`ptr`должно быть определение класса, которое становится родительским классом нерестимого объекта.</span><span class="sxs-lookup"><span data-stu-id="628ea-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="628ea-133">Возвращаемый объект становится подклассом текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="628ea-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="628ea-134">Новый объект, `ppNewClass` возвращенный в автоматически становится подклассом текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="628ea-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="628ea-135">Такое поведение нельзя переопределить.</span><span class="sxs-lookup"><span data-stu-id="628ea-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="628ea-136">Нет другого метода, с помощью которого могут быть созданы подклассы (производные классы).</span><span class="sxs-lookup"><span data-stu-id="628ea-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="628ea-137">Требования</span><span class="sxs-lookup"><span data-stu-id="628ea-137">Requirements</span></span>  
 <span data-ttu-id="628ea-138">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="628ea-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="628ea-139">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="628ea-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="628ea-140">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="628ea-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="628ea-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="628ea-141">See also</span></span>

- [<span data-ttu-id="628ea-142">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="628ea-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
