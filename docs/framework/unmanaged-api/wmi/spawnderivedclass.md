---
title: Функция SpawnDerivedClass (Справочник по неуправляемым API)
description: Функция SpawnDerivedClass создает новый объект, который является производным от объекта.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe93b7ee28db8151345871b0dd716d41227ed565
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462303"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="2b8f6-103">Функция SpawnDerivedClass</span><span class="sxs-lookup"><span data-stu-id="2b8f6-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="2b8f6-104">Создает объект вновь производного класса из указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2b8f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b8f6-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="2b8f6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b8f6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2b8f6-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2b8f6-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="2b8f6-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-109">[in] Reserved.</span></span> <span data-ttu-id="2b8f6-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="2b8f6-111">[out] Получает указатель на новый объект определения класса.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="2b8f6-112">Если возникает ошибка, новый объект не возвращается, и `ppNewClass` влево без изменений.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="2b8f6-113">Его значение не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="2b8f6-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2b8f6-114">Return value</span></span>

<span data-ttu-id="2b8f6-115">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="2b8f6-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2b8f6-116">Константа</span><span class="sxs-lookup"><span data-stu-id="2b8f6-116">Constant</span></span>  |<span data-ttu-id="2b8f6-117">Значение</span><span class="sxs-lookup"><span data-stu-id="2b8f6-117">Value</span></span>  |<span data-ttu-id="2b8f6-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2b8f6-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2b8f6-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="2b8f6-119">0x80041001</span></span> | <span data-ttu-id="2b8f6-120">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="2b8f6-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="2b8f6-121">0x80041016</span></span> | <span data-ttu-id="2b8f6-122">Запрошена недопустимая операция, например создать класс из экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="2b8f6-123">Исходный класс была не полностью определена или зарегистрированы с помощью управления Windows, поэтому нового производного класса не допускается.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2b8f6-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2b8f6-124">0x80041006</span></span> | <span data-ttu-id="2b8f6-125">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2b8f6-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2b8f6-126">0x80041008</span></span> | <span data-ttu-id="2b8f6-127">Свойство `ppNewClass` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2b8f6-128">0</span><span class="sxs-lookup"><span data-stu-id="2b8f6-128">0</span></span> | <span data-ttu-id="2b8f6-129">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2b8f6-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b8f6-130">Remarks</span></span>

<span data-ttu-id="2b8f6-131">Эта функция создает оболочку для вызова [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="2b8f6-132">`ptr` должно быть определение класса, который становится родительский класс, порожденный объекта.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="2b8f6-133">Возвращаемый объект становится подкласс текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="2b8f6-134">Новый объект, возвращаемый в `ppNewClass` автоматически становится подкласс текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="2b8f6-135">Нельзя переопределить это поведение.</span><span class="sxs-lookup"><span data-stu-id="2b8f6-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="2b8f6-136">Нет никакой другой метод, с помощью которого создаются подклассы (классы).</span><span class="sxs-lookup"><span data-stu-id="2b8f6-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b8f6-137">Требования</span><span class="sxs-lookup"><span data-stu-id="2b8f6-137">Requirements</span></span>  
 <span data-ttu-id="2b8f6-138">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b8f6-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b8f6-139">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2b8f6-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2b8f6-140">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2b8f6-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b8f6-141">См. также</span><span class="sxs-lookup"><span data-stu-id="2b8f6-141">See also</span></span>  
[<span data-ttu-id="2b8f6-142">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="2b8f6-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
