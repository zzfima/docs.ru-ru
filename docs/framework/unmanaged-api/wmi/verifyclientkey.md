---
title: Функция VerifyClientKey (Неуправляемая справка API)
description: Функция VerifyClientKey гарантирует, что ключ клиента имеет правильную безопасность.
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
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176712"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="2f916-103">Функция VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="2f916-103">VerifyClientKey function</span></span>
<span data-ttu-id="2f916-104">Проверяет, что ключ клиента имеет верные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="2f916-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2f916-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f916-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="2f916-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f916-106">Return value</span></span>

<span data-ttu-id="2f916-107">Если функция успешно, значение возврата `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="2f916-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="2f916-108">Если функция выходит из строя, значение возврата представляет собой ненулевой код ошибки, определенный в *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="2f916-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f916-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2f916-109">Requirements</span></span>  
 <span data-ttu-id="2f916-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f916-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f916-111">**Заголовок:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="2f916-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="2f916-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2f916-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f916-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2f916-113">See also</span></span>

- [<span data-ttu-id="2f916-114">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="2f916-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
