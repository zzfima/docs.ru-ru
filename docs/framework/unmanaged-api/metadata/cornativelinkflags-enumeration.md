---
title: "Перечисление CorNativeLinkFlags"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c8477ef13c53db6cc4de58c4e707a82e2ab7f650
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="272fd-102">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="272fd-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="272fd-103">Предоставляет значения флагов, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="272fd-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="272fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="272fd-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="272fd-105">Участники</span><span class="sxs-lookup"><span data-stu-id="272fd-105">Members</span></span>  
  
|<span data-ttu-id="272fd-106">Член</span><span class="sxs-lookup"><span data-stu-id="272fd-106">Member</span></span>|<span data-ttu-id="272fd-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="272fd-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="272fd-108">Указывает на отсутствие флагов.</span><span class="sxs-lookup"><span data-stu-id="272fd-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="272fd-109">Указывает `setLastError` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="272fd-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="272fd-110">Указывает `nomangle` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="272fd-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="272fd-111">Не используется.</span><span class="sxs-lookup"><span data-stu-id="272fd-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="272fd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="272fd-112">Requirements</span></span>  
 <span data-ttu-id="272fd-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="272fd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="272fd-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="272fd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="272fd-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="272fd-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="272fd-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="272fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="272fd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="272fd-117">See Also</span></span>  
 [<span data-ttu-id="272fd-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="272fd-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
