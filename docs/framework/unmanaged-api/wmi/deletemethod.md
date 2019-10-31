---
title: Функция DeleteMethod (Справочник по неуправляемым API)
description: Функция DeleteMethod удаляет указанный метод из определения класса CIM.
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
ms.openlocfilehash: db360584dacf250be2f35e5e6666f8332b39a8dd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120649"
---
# <a name="deletemethod-function"></a><span data-ttu-id="f8d0b-103">Функция DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="f8d0b-103">DeleteMethod function</span></span>
<span data-ttu-id="f8d0b-104">Удаляет указанный метод из определения класса CIM.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f8d0b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8d0b-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="f8d0b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8d0b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f8d0b-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f8d0b-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="f8d0b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="f8d0b-109">окне Имя метода, удаляемого из таблицы классов.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="f8d0b-110">`wszName` должен быть указателем на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f8d0b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f8d0b-111">Return value</span></span>

<span data-ttu-id="f8d0b-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="f8d0b-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f8d0b-113">Константа</span><span class="sxs-lookup"><span data-stu-id="f8d0b-113">Constant</span></span>  |<span data-ttu-id="f8d0b-114">значения</span><span class="sxs-lookup"><span data-stu-id="f8d0b-114">Value</span></span>  |<span data-ttu-id="f8d0b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f8d0b-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="f8d0b-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f8d0b-116">0x80041002</span></span> | <span data-ttu-id="f8d0b-117">Указанный метод не существует.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f8d0b-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f8d0b-118">0x80041006</span></span> | <span data-ttu-id="f8d0b-119">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f8d0b-120">0</span><span class="sxs-lookup"><span data-stu-id="f8d0b-120">0</span></span> | <span data-ttu-id="f8d0b-121">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="f8d0b-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="f8d0b-122">Remarks</span></span>

<span data-ttu-id="f8d0b-123">Эта функция создает оболочку для вызова метода [ивбемклассобжект::D елетемесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) .</span><span class="sxs-lookup"><span data-stu-id="f8d0b-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="f8d0b-124">Удаление метода не поддерживается для [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указателей, указывающих на экземпляры CIM.</span><span class="sxs-lookup"><span data-stu-id="f8d0b-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="f8d0b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f8d0b-125">Requirements</span></span>  
 <span data-ttu-id="f8d0b-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8d0b-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8d0b-127">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f8d0b-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f8d0b-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8d0b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d0b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f8d0b-129">See also</span></span>

- [<span data-ttu-id="f8d0b-130">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="f8d0b-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
