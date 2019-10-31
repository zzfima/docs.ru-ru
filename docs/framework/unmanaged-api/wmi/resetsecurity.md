---
title: Функция Ресетсекурити (Справочник по неуправляемым API)
description: Функция Ресетсекурити назначает маркер олицетворения текущему потоку.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 95d91eac21e82e55af2f5e9ab181b770832f5ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120214"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="93472-103">Функция Ресетсекурити</span><span class="sxs-lookup"><span data-stu-id="93472-103">ResetSecurity function</span></span>
<span data-ttu-id="93472-104">Назначает предоставленный маркер олицетворения текущему потоку.</span><span class="sxs-lookup"><span data-stu-id="93472-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="93472-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93472-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="93472-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="93472-106">Parameters</span></span>

`token`  
<span data-ttu-id="93472-107">окне Токен олицетворения, связываемый с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="93472-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="93472-108">Это значение может быть равно `null`.</span><span class="sxs-lookup"><span data-stu-id="93472-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="93472-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="93472-109">Return value</span></span>

<span data-ttu-id="93472-110">Если функция выполнена удачно, возвращается значение `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="93472-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="93472-111">Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="93472-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="93472-112">Чтобы получить расширенные сведения об ошибке, вызовите функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="93472-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="93472-113">Требования</span><span class="sxs-lookup"><span data-stu-id="93472-113">Requirements</span></span>  
 <span data-ttu-id="93472-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93472-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93472-115">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="93472-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="93472-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="93472-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93472-117">См. также</span><span class="sxs-lookup"><span data-stu-id="93472-117">See also</span></span>

- [<span data-ttu-id="93472-118">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="93472-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
