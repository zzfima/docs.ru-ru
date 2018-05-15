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
ms.openlocfilehash: ea8a74633d3e950f6cf7ba87c00a9efa45206545
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="f02a1-103">Функция VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="f02a1-103">VerifyClientKey function</span></span>
<span data-ttu-id="f02a1-104">Гарантирует, что ключ клиента имеет неправильные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="f02a1-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f02a1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f02a1-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="f02a1-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f02a1-106">Return value</span></span>

<span data-ttu-id="f02a1-107">Если функция выполняется успешно, возвращаемое значение равно `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="f02a1-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="f02a1-108">Если функция завершается с ошибкой, возвращается ошибка ненулевой код, определенный в *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="f02a1-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="f02a1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f02a1-109">Requirements</span></span>  
 <span data-ttu-id="f02a1-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f02a1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f02a1-111">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="f02a1-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="f02a1-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f02a1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02a1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f02a1-113">See also</span></span>  
[<span data-ttu-id="f02a1-114">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="f02a1-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
