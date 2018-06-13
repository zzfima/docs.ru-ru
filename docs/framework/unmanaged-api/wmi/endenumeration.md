---
title: Функция EndEnumeration (Справочник по неуправляемым API)
description: Функция EndEnumeration завершает перечисления.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d77497beb122bef580d6eb142fede33b8cf220e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459522"
---
# <a name="endenumeration-function"></a><span data-ttu-id="b50ce-103">Функция EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="b50ce-103">EndEnumeration function</span></span>
<span data-ttu-id="b50ce-104">Завершает последовательность перечисления запущен с помощью вызова [BeginEnumeration функция](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b50ce-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b50ce-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b50ce-105">Syntax</span></span>  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="b50ce-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b50ce-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b50ce-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="b50ce-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b50ce-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b50ce-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>


## <a name="return-value"></a><span data-ttu-id="b50ce-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b50ce-109">Return value</span></span>

<span data-ttu-id="b50ce-110">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="b50ce-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b50ce-111">Константа</span><span class="sxs-lookup"><span data-stu-id="b50ce-111">Constant</span></span>  |<span data-ttu-id="b50ce-112">Значение</span><span class="sxs-lookup"><span data-stu-id="b50ce-112">Value</span></span>  |<span data-ttu-id="b50ce-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b50ce-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b50ce-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b50ce-114">0x80041001</span></span> | <span data-ttu-id="b50ce-115">Произошел общий сбой.</span><span class="sxs-lookup"><span data-stu-id="b50ce-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b50ce-116">0</span><span class="sxs-lookup"><span data-stu-id="b50ce-116">0</span></span> | <span data-ttu-id="b50ce-117">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="b50ce-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b50ce-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="b50ce-118">Remarks</span></span>

<span data-ttu-id="b50ce-119">Эта функция создает оболочку для вызова [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="b50ce-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="b50ce-120">Вызов `EndEnumeration` функция не является обязательным, но рекомендуется, так как он освобождает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="b50ce-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="b50ce-121">Тем не менее ресурс освобождаются автоматически при запуске следующего перечисления или объект освобождается.</span><span class="sxs-lookup"><span data-stu-id="b50ce-121">However, the resoruces are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="b50ce-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b50ce-122">Requirements</span></span>  
 <span data-ttu-id="b50ce-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b50ce-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b50ce-124">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b50ce-124">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b50ce-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b50ce-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b50ce-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b50ce-126">See also</span></span>  
[<span data-ttu-id="b50ce-127">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="b50ce-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
