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
ms.openlocfilehash: 8fe6216e11a64ea182d796247d888b862b1e8377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177930"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="060c1-102">Перечисление CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="060c1-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="060c1-103">Обеспечивает значения флага, используемые для регистрации при установке модуля или композитного изображения.</span><span class="sxs-lookup"><span data-stu-id="060c1-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="060c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="060c1-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="060c1-105">Члены</span><span class="sxs-lookup"><span data-stu-id="060c1-105">Members</span></span>  
  
|<span data-ttu-id="060c1-106">Участник</span><span class="sxs-lookup"><span data-stu-id="060c1-106">Member</span></span>|<span data-ttu-id="060c1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="060c1-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="060c1-108">Уточняется, что файлы не должны быть скопированы в пункт назначения.</span><span class="sxs-lookup"><span data-stu-id="060c1-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="060c1-109">Уточняется, что модуль или композит является конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="060c1-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="060c1-110">Уточняется, что модуль или композит имеет ссылки класса.</span><span class="sxs-lookup"><span data-stu-id="060c1-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="060c1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="060c1-111">Requirements</span></span>  
 <span data-ttu-id="060c1-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="060c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="060c1-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="060c1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="060c1-114">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="060c1-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="060c1-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="060c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060c1-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="060c1-116">See also</span></span>

- [<span data-ttu-id="060c1-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="060c1-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
