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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108450"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="d28c3-102">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="d28c3-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="d28c3-103">Указывает на функцию, которая вызывается средой выполнения (CLR) для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d28c3-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="d28c3-104">Этот указатель функции был объявлен устаревшим в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d28c3-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d28c3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d28c3-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d28c3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d28c3-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d28c3-107">[in] Указатель на непрозрачные памяти, выделенный вызывающим объектом, содержащей управляемый код, который будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="d28c3-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="d28c3-108">Вызывающий объект (CLR) управляет выделением и временем существования этой памяти.</span><span class="sxs-lookup"><span data-stu-id="d28c3-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="d28c3-109">Это не памяти неуправляемой кучи среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d28c3-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d28c3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d28c3-110">Requirements</span></span>  
 <span data-ttu-id="d28c3-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d28c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d28c3-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d28c3-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d28c3-113">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="d28c3-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d28c3-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d28c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28c3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d28c3-115">See also</span></span>

- [<span data-ttu-id="d28c3-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d28c3-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
