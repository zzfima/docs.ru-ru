---
title: Метод IGCThreadControl::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 1e1d63ab28276f69e5b3a762520db8f8300d05bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134763"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="c5ace-102">Метод IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="c5ace-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="c5ace-103">Уведомляет узел о том, что среда выполнения начинает приостановку потока для сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="c5ace-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5ace-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5ace-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5ace-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="c5ace-105">Remarks</span></span>  
 <span data-ttu-id="c5ace-106">Не Перепланируйте потоки во время обратного вызова `SuspensionStarting`.</span><span class="sxs-lookup"><span data-stu-id="c5ace-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5ace-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c5ace-107">Requirements</span></span>  
 <span data-ttu-id="c5ace-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5ace-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5ace-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c5ace-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5ace-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5ace-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5ace-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5ace-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ace-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c5ace-112">See also</span></span>

- [<span data-ttu-id="c5ace-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="c5ace-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
