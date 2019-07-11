---
title: Функция VerifyClientKey (Справочник по неуправляемым API)
description: Функция VerifyClientKey гарантирует, что ключ клиента имеет неправильные параметры безопасности.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b51fe4510f4172227d9afd049eb6815790a165
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783091"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="6338c-103">Функция VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="6338c-103">VerifyClientKey function</span></span>
<span data-ttu-id="6338c-104">Проверяет, что ключ клиента имеет верные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="6338c-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6338c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6338c-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="6338c-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6338c-106">Return value</span></span>

<span data-ttu-id="6338c-107">Если функция выполняется успешно, возвращаемое значение равно `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="6338c-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="6338c-108">Если функция завершается с ошибкой, возвращается код ошибки, определенный в *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="6338c-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="6338c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6338c-109">Requirements</span></span>  
 <span data-ttu-id="6338c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6338c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6338c-111">**Заголовок.** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="6338c-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="6338c-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6338c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6338c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6338c-113">See also</span></span>

- [<span data-ttu-id="6338c-114">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="6338c-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
