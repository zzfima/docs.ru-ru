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
ms.openlocfilehash: 0a072e124343641c9f75fb9f924a6409efc8e1d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719941"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="8fc45-102">Перечисление CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="8fc45-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="8fc45-103">Задает флаги для выбора параметров компоновщика метаданных.</span><span class="sxs-lookup"><span data-stu-id="8fc45-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fc45-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="8fc45-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8fc45-105">Members</span></span>  
  
|<span data-ttu-id="8fc45-106">Член</span><span class="sxs-lookup"><span data-stu-id="8fc45-106">Member</span></span>|<span data-ttu-id="8fc45-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8fc45-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="8fc45-108">Закрытые типы и глобальные функции, не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="8fc45-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="8fc45-109">Закрытые типы и глобальные функции сохраняются.</span><span class="sxs-lookup"><span data-stu-id="8fc45-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8fc45-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8fc45-110">Requirements</span></span>  
 <span data-ttu-id="8fc45-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc45-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc45-112">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8fc45-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8fc45-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc45-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc45-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8fc45-114">See also</span></span>
- [<span data-ttu-id="8fc45-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="8fc45-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
