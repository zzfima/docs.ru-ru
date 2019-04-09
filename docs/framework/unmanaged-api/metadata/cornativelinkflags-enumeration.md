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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152000"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="0f97b-102">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="0f97b-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="0f97b-103">Предоставляет значения флагов, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="0f97b-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f97b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f97b-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0f97b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0f97b-105">Members</span></span>  
  
|<span data-ttu-id="0f97b-106">Член</span><span class="sxs-lookup"><span data-stu-id="0f97b-106">Member</span></span>|<span data-ttu-id="0f97b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0f97b-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="0f97b-108">Указывает флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="0f97b-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="0f97b-109">Указывает `setLastError` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0f97b-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="0f97b-110">Указывает `nomangle` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0f97b-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="0f97b-111">Не используется.</span><span class="sxs-lookup"><span data-stu-id="0f97b-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f97b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0f97b-112">Requirements</span></span>  
 <span data-ttu-id="0f97b-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f97b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f97b-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f97b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f97b-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f97b-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0f97b-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0f97b-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0f97b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0f97b-117">See also</span></span>

- [<span data-ttu-id="0f97b-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0f97b-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
