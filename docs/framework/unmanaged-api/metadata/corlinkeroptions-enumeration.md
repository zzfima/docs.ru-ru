---
title: "Перечисление CorLinkerOptions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLinkerOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorLinkerOptions
helpviewer_keywords: CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9d2eb081c7ef0b4feb414011d7246a1e2d6d8192
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="cc3c1-102">Перечисление CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="cc3c1-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="cc3c1-103">Задает флаги для выбора параметров компоновщика метаданных.</span><span class="sxs-lookup"><span data-stu-id="cc3c1-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc3c1-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="cc3c1-105">Члены</span><span class="sxs-lookup"><span data-stu-id="cc3c1-105">Members</span></span>  
  
|<span data-ttu-id="cc3c1-106">Член</span><span class="sxs-lookup"><span data-stu-id="cc3c1-106">Member</span></span>|<span data-ttu-id="cc3c1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cc3c1-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="cc3c1-108">Закрытые типы и глобальные функции, не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="cc3c1-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="cc3c1-109">Закрытые типы и глобальные функции сохраняются.</span><span class="sxs-lookup"><span data-stu-id="cc3c1-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc3c1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cc3c1-110">Requirements</span></span>  
 <span data-ttu-id="cc3c1-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc3c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc3c1-112">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="cc3c1-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cc3c1-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc3c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3c1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cc3c1-114">See Also</span></span>  
 [<span data-ttu-id="cc3c1-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="cc3c1-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
