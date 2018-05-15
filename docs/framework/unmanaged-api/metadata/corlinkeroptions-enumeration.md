---
title: Перечисление CorLinkerOptions
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d154985e9c1614e6b8f13a55410ead0cb5e861b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="2b23a-102">Перечисление CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="2b23a-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="2b23a-103">Задает флаги для выбора параметров компоновщика метаданных.</span><span class="sxs-lookup"><span data-stu-id="2b23a-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b23a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b23a-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="2b23a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2b23a-105">Members</span></span>  
  
|<span data-ttu-id="2b23a-106">Член</span><span class="sxs-lookup"><span data-stu-id="2b23a-106">Member</span></span>|<span data-ttu-id="2b23a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2b23a-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="2b23a-108">Закрытые типы и глобальные функции, не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="2b23a-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="2b23a-109">Закрытые типы и глобальные функции сохраняются.</span><span class="sxs-lookup"><span data-stu-id="2b23a-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b23a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2b23a-110">Requirements</span></span>  
 <span data-ttu-id="2b23a-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b23a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b23a-112">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2b23a-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2b23a-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b23a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b23a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2b23a-114">See Also</span></span>  
 [<span data-ttu-id="2b23a-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="2b23a-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
