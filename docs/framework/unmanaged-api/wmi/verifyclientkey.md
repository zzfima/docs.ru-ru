---
title: Функция Верификлиенткэй (Справочник по неуправляемым API)
description: Функция Верификлиенткэй обеспечивает правильную защиту ключа клиента.
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
ms.openlocfilehash: 0a0680651eb192e2798ede00048599c5130e63f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107359"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="56efd-103">Функция Верификлиенткэй</span><span class="sxs-lookup"><span data-stu-id="56efd-103">VerifyClientKey function</span></span>
<span data-ttu-id="56efd-104">Проверяет, что ключ клиента имеет верные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="56efd-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="56efd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56efd-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="56efd-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56efd-106">Return value</span></span>

<span data-ttu-id="56efd-107">Если функция выполнена удачно, возвращается значение `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="56efd-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="56efd-108">Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в *файле Winerror. h*.</span><span class="sxs-lookup"><span data-stu-id="56efd-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="56efd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="56efd-109">Requirements</span></span>  
 <span data-ttu-id="56efd-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56efd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56efd-111">**Заголовок:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="56efd-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="56efd-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="56efd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56efd-113">См. также</span><span class="sxs-lookup"><span data-stu-id="56efd-113">See also</span></span>

- [<span data-ttu-id="56efd-114">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="56efd-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
