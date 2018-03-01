---
title: "Метод ICeeGen::GetStringSection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 240fad6c53fc0db3c55296069ca91998b7c530f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="453a5-102">Метод ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="453a5-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="453a5-103">Возвращает строковое представление раздела кода, который ссылается указанный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="453a5-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="453a5-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="453a5-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453a5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="453a5-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="453a5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="453a5-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="453a5-107">[in, out] Дескриптор раздела кода.</span><span class="sxs-lookup"><span data-stu-id="453a5-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="453a5-108">Требования</span><span class="sxs-lookup"><span data-stu-id="453a5-108">Requirements</span></span>  
 <span data-ttu-id="453a5-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="453a5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453a5-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="453a5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="453a5-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="453a5-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="453a5-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453a5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453a5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="453a5-113">See Also</span></span>  
 [<span data-ttu-id="453a5-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="453a5-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
