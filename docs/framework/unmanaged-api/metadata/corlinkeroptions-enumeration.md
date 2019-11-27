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
ms.openlocfilehash: 086e17185df9caa823b44b51cf027f95d635c48d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450270"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="c28e9-102">Перечисление CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="c28e9-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="c28e9-103">Задает флаги для выбора параметров компоновщика метаданных.</span><span class="sxs-lookup"><span data-stu-id="c28e9-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c28e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c28e9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="c28e9-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c28e9-105">Members</span></span>  
  
|<span data-ttu-id="c28e9-106">Член</span><span class="sxs-lookup"><span data-stu-id="c28e9-106">Member</span></span>|<span data-ttu-id="c28e9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c28e9-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="c28e9-108">Закрытые типы и глобальные функции не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="c28e9-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="c28e9-109">Закрытые типы и глобальные функции сохраняются.</span><span class="sxs-lookup"><span data-stu-id="c28e9-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c28e9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c28e9-110">Requirements</span></span>  
 <span data-ttu-id="c28e9-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c28e9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c28e9-112">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="c28e9-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c28e9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c28e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c28e9-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="c28e9-114">See also</span></span>

- [<span data-ttu-id="c28e9-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="c28e9-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
