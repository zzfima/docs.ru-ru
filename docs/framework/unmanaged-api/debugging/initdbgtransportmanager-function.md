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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423667"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="4074f-102">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="4074f-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="4074f-103">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4074f-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4074f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4074f-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4074f-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4074f-105">Return Value</span></span>  
 <span data-ttu-id="4074f-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="4074f-106">S_OK</span></span>  
 <span data-ttu-id="4074f-107">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="4074f-107">Success.</span></span>  
  
 <span data-ttu-id="4074f-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4074f-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4074f-109">Функции не удалось выделить память для диспетчера транспорта.</span><span class="sxs-lookup"><span data-stu-id="4074f-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="4074f-110">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="4074f-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="4074f-111">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="4074f-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4074f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4074f-112">Requirements</span></span>  
 <span data-ttu-id="4074f-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4074f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4074f-114">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="4074f-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="4074f-115">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="4074f-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="4074f-116">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4074f-116">**.NET Framework Versions:** 3.5 SP1</span></span>
