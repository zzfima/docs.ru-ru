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
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782490"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="f101d-103">Функция VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="f101d-103">VerifyClientKey function</span></span>
<span data-ttu-id="f101d-104">Проверяет, что ключ клиента имеет верные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="f101d-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f101d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f101d-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="f101d-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f101d-106">Return value</span></span>

<span data-ttu-id="f101d-107">Если функция выполняется успешно, возвращаемое значение равно `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="f101d-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="f101d-108">Если функция завершается с ошибкой, возвращается код ошибки, определенный в *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="f101d-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="f101d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f101d-109">Requirements</span></span>  
 <span data-ttu-id="f101d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f101d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f101d-111">**Заголовок.** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="f101d-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="f101d-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f101d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f101d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f101d-113">See also</span></span>

- [<span data-ttu-id="f101d-114">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="f101d-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
