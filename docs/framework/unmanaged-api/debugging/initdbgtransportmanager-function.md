---
title: Функция InitDbgTransportManager
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 948e97064d12dc5b2044faf35aa374e5ba5f2592
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764781"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="f59d1-102">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="f59d1-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="f59d1-103">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f59d1-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f59d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f59d1-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f59d1-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f59d1-105">Return Value</span></span>  
 <span data-ttu-id="f59d1-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="f59d1-106">S_OK</span></span>  
 <span data-ttu-id="f59d1-107">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="f59d1-107">Success.</span></span>  
  
 <span data-ttu-id="f59d1-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f59d1-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="f59d1-109">Функции не удалось выделить память для диспетчера транспорта.</span><span class="sxs-lookup"><span data-stu-id="f59d1-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="f59d1-110">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="f59d1-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f59d1-111">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="f59d1-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f59d1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f59d1-112">Requirements</span></span>  
 <span data-ttu-id="f59d1-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f59d1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f59d1-114">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="f59d1-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="f59d1-115">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="f59d1-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="f59d1-116">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f59d1-116">**.NET Framework Versions:** 3.5 SP1</span></span>
