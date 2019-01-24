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
ms.openlocfilehash: 94d601125049f0c215b3b03bf8b13d2959872c3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711763"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="fe967-103">Функция VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="fe967-103">VerifyClientKey function</span></span>
<span data-ttu-id="fe967-104">Проверяет, что ключ клиента имеет верные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="fe967-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fe967-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe967-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="fe967-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe967-106">Return value</span></span>

<span data-ttu-id="fe967-107">Если функция выполняется успешно, возвращаемое значение равно `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="fe967-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="fe967-108">Если функция завершается с ошибкой, возвращается код ошибки, определенный в *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="fe967-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe967-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fe967-109">Requirements</span></span>  
 <span data-ttu-id="fe967-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe967-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe967-111">**Заголовок.** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="fe967-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="fe967-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fe967-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe967-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fe967-113">See also</span></span>
- [<span data-ttu-id="fe967-114">WMI и счетчики производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="fe967-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
