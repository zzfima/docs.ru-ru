---
title: Функция DeleteMethod (Справочник по неуправляемым API)
description: Функция DeleteMethod Удаляет указанный метод из определения класса CIM.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eb96a75686a14182b9526a0832223c2b9abfc34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136920"
---
# <a name="deletemethod-function"></a><span data-ttu-id="0b9bf-103">Функция DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="0b9bf-103">DeleteMethod function</span></span>
<span data-ttu-id="0b9bf-104">Удаляет указанный метод из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0b9bf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b9bf-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="0b9bf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b9bf-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0b9bf-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0b9bf-108">[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="0b9bf-109">[in] Имя метода для удаления из класса в таблицу.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-109">[in] The name of the method to remove from the class table.</span></span> `wszName` <span data-ttu-id="0b9bf-110">должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-110">must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="0b9bf-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b9bf-111">Return value</span></span>

<span data-ttu-id="0b9bf-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="0b9bf-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0b9bf-113">Константа</span><span class="sxs-lookup"><span data-stu-id="0b9bf-113">Constant</span></span>  |<span data-ttu-id="0b9bf-114">Значение</span><span class="sxs-lookup"><span data-stu-id="0b9bf-114">Value</span></span>  |<span data-ttu-id="0b9bf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0b9bf-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="0b9bf-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0b9bf-116">0x80041002</span></span> | <span data-ttu-id="0b9bf-117">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0b9bf-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0b9bf-118">0x80041006</span></span> | <span data-ttu-id="0b9bf-119">Не хватает памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0b9bf-120">0</span><span class="sxs-lookup"><span data-stu-id="0b9bf-120">0</span></span> | <span data-ttu-id="0b9bf-121">Вызов функции был успешным.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0b9bf-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b9bf-122">Remarks</span></span>

<span data-ttu-id="0b9bf-123">Эта функция создает оболочку для вызова [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) метод.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="0b9bf-124">Удаление метода не поддерживается для [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указатели, которые указывают на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="0b9bf-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b9bf-125">Требования</span><span class="sxs-lookup"><span data-stu-id="0b9bf-125">Requirements</span></span>  
 <span data-ttu-id="0b9bf-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b9bf-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b9bf-127">**Заголовок.** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0b9bf-127">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="0b9bf-128">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0b9bf-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b9bf-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0b9bf-129">See also</span></span>

- [<span data-ttu-id="0b9bf-130">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="0b9bf-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
