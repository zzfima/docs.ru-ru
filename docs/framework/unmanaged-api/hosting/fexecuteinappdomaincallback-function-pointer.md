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
ms.openlocfilehash: 970468bc2f50144c62c6e3cbcf9c00c2027f7663
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138178"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="9e8e1-102">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="9e8e1-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="9e8e1-103">Указывает на функцию, которая вызывается средой CLR для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9e8e1-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="9e8e1-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9e8e1-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e8e1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e8e1-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e8e1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e8e1-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="9e8e1-107">окне Указатель на непрозрачную память, выделенную вызывающим объектом, содержащую управляемый код для выполнения.</span><span class="sxs-lookup"><span data-stu-id="9e8e1-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="9e8e1-108">Выделение и время существования этой памяти управляются вызывающим объектом (то есть средой CLR).</span><span class="sxs-lookup"><span data-stu-id="9e8e1-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="9e8e1-109">Это не управляемая средой CLR память в куче.</span><span class="sxs-lookup"><span data-stu-id="9e8e1-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e8e1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9e8e1-110">Requirements</span></span>  
 <span data-ttu-id="9e8e1-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e8e1-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9e8e1-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e8e1-113">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="9e8e1-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="9e8e1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8e1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9e8e1-115">See also</span></span>

- [<span data-ttu-id="9e8e1-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="9e8e1-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
