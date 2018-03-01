---
title: "Перечисление CorLinkerOptions"
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
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65914e52228bf55a35d48bfbf036c8bb78b29c2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="f071d-102">Перечисление CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="f071d-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="f071d-103">Задает флаги для выбора параметров компоновщика метаданных.</span><span class="sxs-lookup"><span data-stu-id="f071d-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f071d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f071d-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="f071d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f071d-105">Members</span></span>  
  
|<span data-ttu-id="f071d-106">Член</span><span class="sxs-lookup"><span data-stu-id="f071d-106">Member</span></span>|<span data-ttu-id="f071d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="f071d-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="f071d-108">Закрытые типы и глобальные функции, не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="f071d-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="f071d-109">Закрытые типы и глобальные функции сохраняются.</span><span class="sxs-lookup"><span data-stu-id="f071d-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f071d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f071d-110">Requirements</span></span>  
 <span data-ttu-id="f071d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f071d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f071d-112">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f071d-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f071d-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f071d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f071d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f071d-114">See Also</span></span>  
 [<span data-ttu-id="f071d-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="f071d-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
