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
ms.openlocfilehash: 2d67bee3ea0e57080179b3fbb7e0b4193860c44d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103292"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="49bf2-102">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="49bf2-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="49bf2-103">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="49bf2-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49bf2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49bf2-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="49bf2-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49bf2-105">Return Value</span></span>  
 <span data-ttu-id="49bf2-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="49bf2-106">S_OK</span></span>  
 <span data-ttu-id="49bf2-107">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="49bf2-107">Success.</span></span>  
  
 <span data-ttu-id="49bf2-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="49bf2-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="49bf2-109">Функции не удалось выделить память для диспетчера транспорта.</span><span class="sxs-lookup"><span data-stu-id="49bf2-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="49bf2-110">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="49bf2-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="49bf2-111">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="49bf2-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49bf2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="49bf2-112">Requirements</span></span>  
 <span data-ttu-id="49bf2-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49bf2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49bf2-114">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="49bf2-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="49bf2-115">**Библиотека:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="49bf2-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="49bf2-116">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="49bf2-116">**.NET Framework Versions:** 3.5 SP1</span></span>
