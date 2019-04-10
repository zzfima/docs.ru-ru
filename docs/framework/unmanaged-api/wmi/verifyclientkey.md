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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214719"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="4f79b-103">Функция VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="4f79b-103">VerifyClientKey function</span></span>
<span data-ttu-id="4f79b-104">Проверяет, что ключ клиента имеет верные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="4f79b-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4f79b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f79b-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="4f79b-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4f79b-106">Return value</span></span>

<span data-ttu-id="4f79b-107">Если функция выполняется успешно, возвращаемое значение равно `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="4f79b-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="4f79b-108">Если функция завершается с ошибкой, возвращается код ошибки, определенный в *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="4f79b-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f79b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4f79b-109">Requirements</span></span>  
 <span data-ttu-id="4f79b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f79b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f79b-111">**Заголовок.** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="4f79b-111">**Header:** WMINet_Utils.def</span></span>  
  
 **<span data-ttu-id="4f79b-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4f79b-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f79b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4f79b-113">See also</span></span>

- [<span data-ttu-id="4f79b-114">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="4f79b-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
