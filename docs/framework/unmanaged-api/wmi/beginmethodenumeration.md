---
title: Функция Бегинмесоденумератион (Справочник по неуправляемым API)
description: Функция Бегинмесоденумератион начинает перечислить методы объекта
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a27787052757098d4edb2d8516e22d8a03b7009a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138789"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="1a1cb-103">Функция BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="1a1cb-103">BeginEnumeration function</span></span>
<span data-ttu-id="1a1cb-104">Начинает перечисление методов, доступных для объекта.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1a1cb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a1cb-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="1a1cb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a1cb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1a1cb-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1a1cb-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="1a1cb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="1a1cb-109">окне Ноль (0) для всех методов или флаг, указывающий область перечисления.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="1a1cb-110">Следующие флаги определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1a1cb-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="1a1cb-111">Константа</span><span class="sxs-lookup"><span data-stu-id="1a1cb-111">Constant</span></span>  |<span data-ttu-id="1a1cb-112">значения</span><span class="sxs-lookup"><span data-stu-id="1a1cb-112">Value</span></span>  |<span data-ttu-id="1a1cb-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1a1cb-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="1a1cb-114">0x10</span><span class="sxs-lookup"><span data-stu-id="1a1cb-114">0x10</span></span> | <span data-ttu-id="1a1cb-115">Ограничьте перечисление методами, определенными в самом классе.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="1a1cb-116">0x20</span><span class="sxs-lookup"><span data-stu-id="1a1cb-116">0x20</span></span> | <span data-ttu-id="1a1cb-117">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="1a1cb-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1a1cb-118">Return value</span></span>

<span data-ttu-id="1a1cb-119">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1a1cb-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1a1cb-120">Константа</span><span class="sxs-lookup"><span data-stu-id="1a1cb-120">Constant</span></span>  |<span data-ttu-id="1a1cb-121">значения</span><span class="sxs-lookup"><span data-stu-id="1a1cb-121">Value</span></span>  |<span data-ttu-id="1a1cb-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1a1cb-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1a1cb-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1a1cb-123">0x80041008</span></span> | <span data-ttu-id="1a1cb-124">`lEnnumFlags` не равно нулю и не является одним из указанных флагов.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1a1cb-125">0</span><span class="sxs-lookup"><span data-stu-id="1a1cb-125">0</span></span> | <span data-ttu-id="1a1cb-126">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1a1cb-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="1a1cb-127">Remarks</span></span>

<span data-ttu-id="1a1cb-128">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: бегинмесоденумератион](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) .</span><span class="sxs-lookup"><span data-stu-id="1a1cb-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="1a1cb-129">Этот вызов метода поддерживается, только если текущий объект является определением класса.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="1a1cb-130">Управление методами недоступно из [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры.</span><span class="sxs-lookup"><span data-stu-id="1a1cb-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="1a1cb-131">Порядок, в котором перечисляются методы, гарантированно является инвариантным для заданного экземпляра [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="1a1cb-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="1a1cb-132">Требования</span><span class="sxs-lookup"><span data-stu-id="1a1cb-132">Requirements</span></span>  
 <span data-ttu-id="1a1cb-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a1cb-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a1cb-134">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="1a1cb-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1a1cb-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1a1cb-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a1cb-136">См. также</span><span class="sxs-lookup"><span data-stu-id="1a1cb-136">See also</span></span>

- [<span data-ttu-id="1a1cb-137">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="1a1cb-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
