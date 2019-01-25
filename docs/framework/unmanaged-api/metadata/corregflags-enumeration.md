---
title: Перечисление CorRegFlags
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52b59a4e52d3e0cda7353ec1b39c5307bd7b218e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532270"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="5721a-102">Перечисление CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="5721a-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="5721a-103">Предоставляет значения флагов, используемые для регистрации при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="5721a-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5721a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5721a-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5721a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5721a-105">Members</span></span>  
  
|<span data-ttu-id="5721a-106">Член</span><span class="sxs-lookup"><span data-stu-id="5721a-106">Member</span></span>|<span data-ttu-id="5721a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="5721a-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="5721a-108">Указывает, что файлы не должны копироваться в назначение.</span><span class="sxs-lookup"><span data-stu-id="5721a-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="5721a-109">Указывает, что модуль или составной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5721a-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="5721a-110">Указывает, что модуль или составной имеет ссылки на класс.</span><span class="sxs-lookup"><span data-stu-id="5721a-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5721a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5721a-111">Requirements</span></span>  
 <span data-ttu-id="5721a-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5721a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5721a-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5721a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5721a-114">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5721a-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5721a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5721a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5721a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5721a-116">See also</span></span>
- [<span data-ttu-id="5721a-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="5721a-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
