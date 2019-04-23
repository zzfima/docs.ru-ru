---
title: Перечисление CorNativeLinkFlags
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e6eb2a30dd6722309fd80c1611ad9200ab14ae5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152000"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="7f80c-102">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="7f80c-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="7f80c-103">Предоставляет значения флагов, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="7f80c-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f80c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f80c-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7f80c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7f80c-105">Members</span></span>  
  
|<span data-ttu-id="7f80c-106">Член</span><span class="sxs-lookup"><span data-stu-id="7f80c-106">Member</span></span>|<span data-ttu-id="7f80c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7f80c-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="7f80c-108">Указывает флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="7f80c-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="7f80c-109">Указывает `setLastError` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7f80c-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="7f80c-110">Указывает `nomangle` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7f80c-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="7f80c-111">Не используется.</span><span class="sxs-lookup"><span data-stu-id="7f80c-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f80c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7f80c-112">Requirements</span></span>  
 <span data-ttu-id="7f80c-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f80c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f80c-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7f80c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f80c-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f80c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f80c-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f80c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f80c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7f80c-117">See also</span></span>

- [<span data-ttu-id="7f80c-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7f80c-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
