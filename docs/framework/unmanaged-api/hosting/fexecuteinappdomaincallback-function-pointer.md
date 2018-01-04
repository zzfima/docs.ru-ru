---
title: "Указатель функции FExecuteInAppDomainCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FExecuteInAppDomainCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: FExecuteInAppDomainCallback
helpviewer_keywords: FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9852abbf2f69dda5c4c3b06f48adbd1bc33f5a1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="35453-102">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="35453-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="35453-103">Указывает на функцию, которая вызывается средой выполнения (CLR) для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="35453-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="35453-104">Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35453-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35453-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35453-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35453-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="35453-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="35453-107">[in] Указатель на непрозрачные выделенный вызывающим объектом памяти, содержащей управляемый код, выполняемый.</span><span class="sxs-lookup"><span data-stu-id="35453-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="35453-108">Вызывающего объекта (CLR) управляет выделением и временем существования этой памяти.</span><span class="sxs-lookup"><span data-stu-id="35453-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="35453-109">Это не управляемая куча память CLR.</span><span class="sxs-lookup"><span data-stu-id="35453-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35453-110">Требования</span><span class="sxs-lookup"><span data-stu-id="35453-110">Requirements</span></span>  
 <span data-ttu-id="35453-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35453-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35453-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35453-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35453-113">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="35453-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="35453-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35453-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35453-115">См. также</span><span class="sxs-lookup"><span data-stu-id="35453-115">See Also</span></span>  
 [<span data-ttu-id="35453-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="35453-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
