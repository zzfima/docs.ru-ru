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
ms.openlocfilehash: eb6b303fa7569712c854e8dc4e7513d8608e2519
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104966"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="869b5-102">Перечисление CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="869b5-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="869b5-103">Предоставляет значения флагов, используемые для регистрации при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="869b5-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="869b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="869b5-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="869b5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="869b5-105">Members</span></span>  
  
|<span data-ttu-id="869b5-106">Член</span><span class="sxs-lookup"><span data-stu-id="869b5-106">Member</span></span>|<span data-ttu-id="869b5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="869b5-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="869b5-108">Указывает, что файлы не должны копироваться в назначение.</span><span class="sxs-lookup"><span data-stu-id="869b5-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="869b5-109">Указывает, что модуль или составной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="869b5-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="869b5-110">Указывает, что модуль или составной имеет ссылки на класс.</span><span class="sxs-lookup"><span data-stu-id="869b5-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="869b5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="869b5-111">Requirements</span></span>  
 <span data-ttu-id="869b5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="869b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="869b5-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="869b5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="869b5-114">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="869b5-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="869b5-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="869b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869b5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="869b5-116">See also</span></span>

- [<span data-ttu-id="869b5-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="869b5-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
