---
title: Указатель функции FExecuteInAppDomainCallback
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9981e97e3be58f6646612dc5c3a50a9e7650e376
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628123"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="d673c-102">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="d673c-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="d673c-103">Указывает на функцию, которая вызывается средой выполнения (CLR) для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d673c-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="d673c-104">Этот указатель функции был объявлен устаревшим в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d673c-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d673c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d673c-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d673c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d673c-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d673c-107">[in] Указатель на непрозрачные памяти, выделенный вызывающим объектом, содержащей управляемый код, который будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="d673c-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="d673c-108">Вызывающий объект (CLR) управляет выделением и временем существования этой памяти.</span><span class="sxs-lookup"><span data-stu-id="d673c-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="d673c-109">Это не памяти неуправляемой кучи среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d673c-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d673c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d673c-110">Requirements</span></span>  
 <span data-ttu-id="d673c-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d673c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d673c-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d673c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d673c-113">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="d673c-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d673c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d673c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d673c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d673c-115">See also</span></span>

- [<span data-ttu-id="d673c-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d673c-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
