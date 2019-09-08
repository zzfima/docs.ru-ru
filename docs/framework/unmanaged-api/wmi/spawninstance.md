---
title: Функция Спавнинстанце (Справочник по неуправляемым API)
description: Функция Спавнинстанце создает новый экземпляр класса.
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
ms.openlocfilehash: 529905bd9286520a8e09479bfc95ef0b614f53e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798217"
---
# <a name="spawninstance-function"></a><span data-ttu-id="15b34-103">Функция Спавнинстанце</span><span class="sxs-lookup"><span data-stu-id="15b34-103">SpawnInstance function</span></span>
<span data-ttu-id="15b34-104">Создает экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="15b34-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="15b34-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15b34-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="15b34-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="15b34-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="15b34-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="15b34-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="15b34-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="15b34-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="15b34-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="15b34-109">[in] Reserved.</span></span> <span data-ttu-id="15b34-110">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="15b34-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="15b34-111">заполняет Получает указатель на новый экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="15b34-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="15b34-112">При возникновении ошибки новый объект не возвращается и `ppNewInstance` остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="15b34-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="15b34-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="15b34-113">Return value</span></span>

<span data-ttu-id="15b34-114">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="15b34-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="15b34-115">Константа</span><span class="sxs-lookup"><span data-stu-id="15b34-115">Constant</span></span>  |<span data-ttu-id="15b34-116">Значение</span><span class="sxs-lookup"><span data-stu-id="15b34-116">Value</span></span>  |<span data-ttu-id="15b34-117">Описание</span><span class="sxs-lookup"><span data-stu-id="15b34-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="15b34-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="15b34-118">0x80041020</span></span> | <span data-ttu-id="15b34-119">`ptr`не является допустимым определением класса и не может порождать новые экземпляры.</span><span class="sxs-lookup"><span data-stu-id="15b34-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="15b34-120">Либо он неполон, либо не зарегистрирован в службе управления Windows путем вызова [путклассвми](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="15b34-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="15b34-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="15b34-121">0x80041006</span></span> | <span data-ttu-id="15b34-122">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="15b34-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="15b34-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="15b34-123">0x80041008</span></span> | <span data-ttu-id="15b34-124">Свойство `ppNewClass` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="15b34-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="15b34-125">0</span><span class="sxs-lookup"><span data-stu-id="15b34-125">0</span></span> | <span data-ttu-id="15b34-126">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="15b34-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="15b34-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="15b34-127">Remarks</span></span>

<span data-ttu-id="15b34-128">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: спавнинстанце](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) .</span><span class="sxs-lookup"><span data-stu-id="15b34-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="15b34-129">`ptr`должно быть определением класса, полученным из системы управления Windows.</span><span class="sxs-lookup"><span data-stu-id="15b34-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="15b34-130">(Обратите внимание, что порождение экземпляра из экземпляра поддерживается, но возвращаемый экземпляр пуст.) Затем это определение класса используется для создания новых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="15b34-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="15b34-131">Вызов функции [путинстанцевми](putinstancewmi.md) требуется, если вы планируете записать экземпляр в Windows Management.</span><span class="sxs-lookup"><span data-stu-id="15b34-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="15b34-132">Новый объект, возвращенный `ppNewClass` в, автоматически станет подклассом текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="15b34-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="15b34-133">Это поведение не может быть переопределено.</span><span class="sxs-lookup"><span data-stu-id="15b34-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="15b34-134">Нет других методов, с помощью которых можно создать подклассы (производные классы).</span><span class="sxs-lookup"><span data-stu-id="15b34-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="15b34-135">Требования</span><span class="sxs-lookup"><span data-stu-id="15b34-135">Requirements</span></span>  
 <span data-ttu-id="15b34-136">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15b34-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b34-137">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="15b34-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="15b34-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15b34-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b34-139">См. также</span><span class="sxs-lookup"><span data-stu-id="15b34-139">See also</span></span>

- [<span data-ttu-id="15b34-140">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="15b34-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
