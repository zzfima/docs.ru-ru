---
title: Функция SpawnInstance (Неуправляемая ссылка API)
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
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176725"
---
# <a name="spawninstance-function"></a><span data-ttu-id="39c63-103">Функция SpawnInstance</span><span class="sxs-lookup"><span data-stu-id="39c63-103">SpawnInstance function</span></span>
<span data-ttu-id="39c63-104">Создает экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="39c63-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="39c63-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39c63-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="39c63-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="39c63-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="39c63-107">(в) Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="39c63-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="39c63-108">(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="39c63-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="39c63-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="39c63-109">[in] Reserved.</span></span> <span data-ttu-id="39c63-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="39c63-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="39c63-111">(ваут) Получает указатель на новый экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="39c63-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="39c63-112">При возникновении ошибки новый объект `ppNewInstance` не возвращается и остается неизмененным.</span><span class="sxs-lookup"><span data-stu-id="39c63-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="39c63-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="39c63-113">Return value</span></span>

<span data-ttu-id="39c63-114">Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="39c63-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="39c63-115">Постоянно</span><span class="sxs-lookup"><span data-stu-id="39c63-115">Constant</span></span>  |<span data-ttu-id="39c63-116">Значение</span><span class="sxs-lookup"><span data-stu-id="39c63-116">Value</span></span>  |<span data-ttu-id="39c63-117">Описание</span><span class="sxs-lookup"><span data-stu-id="39c63-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="39c63-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="39c63-118">0x80041020</span></span> | <span data-ttu-id="39c63-119">`ptr`не является действительным определением класса и не может породить новые экземпляры.</span><span class="sxs-lookup"><span data-stu-id="39c63-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="39c63-120">Либо она неполная, либо она не была зарегистрирована в управлении Windows, позвонив [в PutClassWmi.](putclasswmi.md)</span><span class="sxs-lookup"><span data-stu-id="39c63-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="39c63-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="39c63-121">0x80041006</span></span> | <span data-ttu-id="39c63-122">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="39c63-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="39c63-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="39c63-123">0x80041008</span></span> | <span data-ttu-id="39c63-124">Параметр `ppNewClass` равен `null`.</span><span class="sxs-lookup"><span data-stu-id="39c63-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="39c63-125">0</span><span class="sxs-lookup"><span data-stu-id="39c63-125">0</span></span> | <span data-ttu-id="39c63-126">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="39c63-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="39c63-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="39c63-127">Remarks</span></span>

<span data-ttu-id="39c63-128">Эта функция завершает вызов методом [IWbemClassObject::SpawnInstance.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)</span><span class="sxs-lookup"><span data-stu-id="39c63-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="39c63-129">`ptr`должно быть определение класса, полученное от управления Windows.</span><span class="sxs-lookup"><span data-stu-id="39c63-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="39c63-130">(Обратите внимание, что нерест экземпляра из экземпляра поддерживается, но возвращенный экземпляр пуст.) Затем это определение класса используется для создания новых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="39c63-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="39c63-131">Если вы намереваетесь написать экземпляр в управление Windows, требуется вызов функции [PutInstanceWmi.](putinstancewmi.md)</span><span class="sxs-lookup"><span data-stu-id="39c63-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="39c63-132">Новый объект, `ppNewClass` возвращенный в автоматически становится подклассом текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="39c63-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="39c63-133">Такое поведение нельзя переопределить.</span><span class="sxs-lookup"><span data-stu-id="39c63-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="39c63-134">Нет другого метода, с помощью которого могут быть созданы подклассы (производные классы).</span><span class="sxs-lookup"><span data-stu-id="39c63-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="39c63-135">Требования</span><span class="sxs-lookup"><span data-stu-id="39c63-135">Requirements</span></span>  
 <span data-ttu-id="39c63-136">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c63-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c63-137">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="39c63-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="39c63-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39c63-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c63-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="39c63-139">See also</span></span>

- [<span data-ttu-id="39c63-140">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="39c63-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
