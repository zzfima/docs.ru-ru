---
title: Clone, функция (ссылка на неуправляемый API)
description: Функция Clone возвращает новый объект, являющийся полным клоном текущего.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c8e7781a3efe7679ef2e05747862911db88bcc5f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141611"
---
# <a name="clone-function"></a><span data-ttu-id="48319-103">Функция Clone</span><span class="sxs-lookup"><span data-stu-id="48319-103">Clone function</span></span>
<span data-ttu-id="48319-104">Возвращает новый объект, который является полным клоном текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="48319-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="48319-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48319-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="48319-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="48319-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="48319-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="48319-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="48319-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="48319-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="48319-109">заполняет Новый объект, который является полной частью `ptr`.</span><span class="sxs-lookup"><span data-stu-id="48319-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="48319-110">Этот аргумент не может быть `null`, если он получает копию текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="48319-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="48319-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="48319-111">Return value</span></span>

<span data-ttu-id="48319-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="48319-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="48319-113">Константа</span><span class="sxs-lookup"><span data-stu-id="48319-113">Constant</span></span>  |<span data-ttu-id="48319-114">значения</span><span class="sxs-lookup"><span data-stu-id="48319-114">Value</span></span>  |<span data-ttu-id="48319-115">Описание</span><span class="sxs-lookup"><span data-stu-id="48319-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="48319-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="48319-116">0x80041001</span></span> | <span data-ttu-id="48319-117">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="48319-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="48319-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="48319-118">0x80041008</span></span> | <span data-ttu-id="48319-119">`null` был указан в качестве параметра и не является допустимым в этом использовании.</span><span class="sxs-lookup"><span data-stu-id="48319-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="48319-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="48319-120">0x80041006</span></span> | <span data-ttu-id="48319-121">Недостаточно памяти для клонирования объекта.</span><span class="sxs-lookup"><span data-stu-id="48319-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="48319-122">0</span><span class="sxs-lookup"><span data-stu-id="48319-122">0</span></span> | <span data-ttu-id="48319-123">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="48319-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="48319-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="48319-124">Remarks</span></span>

<span data-ttu-id="48319-125">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="48319-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="48319-126">Клонированный объект представляет собой COM-объект со счетчиком ссылок, равным 1.</span><span class="sxs-lookup"><span data-stu-id="48319-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="48319-127">Требования</span><span class="sxs-lookup"><span data-stu-id="48319-127">Requirements</span></span>  
 <span data-ttu-id="48319-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48319-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48319-129">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="48319-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="48319-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="48319-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48319-131">См. также</span><span class="sxs-lookup"><span data-stu-id="48319-131">See also</span></span>

- [<span data-ttu-id="48319-132">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="48319-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
