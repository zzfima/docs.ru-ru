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
ms.openlocfilehash: 74cb2c7d1f79d23e1331cc7192ba2d6acfd9835c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761654"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="91b64-102">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="91b64-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="91b64-103">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="91b64-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91b64-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="91b64-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="91b64-105">Return Value</span></span>  
 <span data-ttu-id="91b64-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="91b64-106">S_OK</span></span>  
 <span data-ttu-id="91b64-107">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="91b64-107">Success.</span></span>  
  
 <span data-ttu-id="91b64-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="91b64-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="91b64-109">Функции не удалось выделить память для диспетчера транспорта.</span><span class="sxs-lookup"><span data-stu-id="91b64-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="91b64-110">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="91b64-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="91b64-111">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="91b64-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91b64-112">Требования</span><span class="sxs-lookup"><span data-stu-id="91b64-112">Requirements</span></span>  
 <span data-ttu-id="91b64-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91b64-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91b64-114">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="91b64-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="91b64-115">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="91b64-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="91b64-116">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="91b64-116">**.NET Framework Versions:** 3.5 SP1</span></span>
