---
title: Функция SpawnInstance (Справочник по неуправляемым API)
description: Функция SpawnInstance создает новый экземпляр класса.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb187719ff502abe61ac5deb69c6427a4a64ab44
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44059685"
---
# <a name="spawninstance-function"></a><span data-ttu-id="856fb-103">Функция SpawnInstance</span><span class="sxs-lookup"><span data-stu-id="856fb-103">SpawnInstance function</span></span>
<span data-ttu-id="856fb-104">Создает экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="856fb-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="856fb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="856fb-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="856fb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="856fb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="856fb-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="856fb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="856fb-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="856fb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="856fb-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="856fb-109">[in] Reserved.</span></span> <span data-ttu-id="856fb-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="856fb-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="856fb-111">[out] Получает указатель на новый экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="856fb-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="856fb-112">Если возникает ошибка, объект не возвращается, и `ppNewInstance` слева без изменений.</span><span class="sxs-lookup"><span data-stu-id="856fb-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="856fb-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="856fb-113">Return value</span></span>

<span data-ttu-id="856fb-114">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="856fb-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="856fb-115">Константа</span><span class="sxs-lookup"><span data-stu-id="856fb-115">Constant</span></span>  |<span data-ttu-id="856fb-116">Значение</span><span class="sxs-lookup"><span data-stu-id="856fb-116">Value</span></span>  |<span data-ttu-id="856fb-117">Описание</span><span class="sxs-lookup"><span data-stu-id="856fb-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="856fb-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="856fb-118">0x80041020</span></span> | <span data-ttu-id="856fb-119">`ptr` не является допустимым определением класса и не может создавать новые экземпляры.</span><span class="sxs-lookup"><span data-stu-id="856fb-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="856fb-120">Он не полон, либо он не был зарегистрирован с помощью службы управления Windows, вызвав [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="856fb-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="856fb-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="856fb-121">0x80041006</span></span> | <span data-ttu-id="856fb-122">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="856fb-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="856fb-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="856fb-123">0x80041008</span></span> | <span data-ttu-id="856fb-124">Свойство `ppNewClass` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="856fb-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="856fb-125">0</span><span class="sxs-lookup"><span data-stu-id="856fb-125">0</span></span> | <span data-ttu-id="856fb-126">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="856fb-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="856fb-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="856fb-127">Remarks</span></span>

<span data-ttu-id="856fb-128">Эта функция создает оболочку для вызова [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) метод.</span><span class="sxs-lookup"><span data-stu-id="856fb-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="856fb-129">`ptr` Определение класса приобретаются у управления Windows.</span><span class="sxs-lookup"><span data-stu-id="856fb-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="856fb-130">(Обратите внимание, что порождает экземпляра из экземпляра поддерживается, но возвращаемый экземпляр является пустым.) Затем можно использовать это определение класса для создания новых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="856fb-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="856fb-131">Вызов [PutInstanceWmi](putinstancewmi.md) функции является обязательным, если вы собираетесь записать экземпляр для управления Windows.</span><span class="sxs-lookup"><span data-stu-id="856fb-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="856fb-132">Новый объект, возвращаемый в `ppNewClass` автоматически становится подкласс текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="856fb-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="856fb-133">Не удается переопределить это поведение.</span><span class="sxs-lookup"><span data-stu-id="856fb-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="856fb-134">Нет никакой другой метод, по которой можно создавать подклассы (производные классы).</span><span class="sxs-lookup"><span data-stu-id="856fb-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="856fb-135">Требования</span><span class="sxs-lookup"><span data-stu-id="856fb-135">Requirements</span></span>  
 <span data-ttu-id="856fb-136">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856fb-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="856fb-137">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="856fb-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="856fb-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="856fb-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856fb-139">См. также</span><span class="sxs-lookup"><span data-stu-id="856fb-139">See also</span></span>  
[<span data-ttu-id="856fb-140">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="856fb-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
