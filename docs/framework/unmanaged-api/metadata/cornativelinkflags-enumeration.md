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
ms.openlocfilehash: 98a83a64a692955d5627e891e7fb3a3ef6f53476
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="acfe8-102">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="acfe8-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="acfe8-103">Предоставляет значения флагов, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="acfe8-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acfe8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acfe8-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="acfe8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="acfe8-105">Members</span></span>  
  
|<span data-ttu-id="acfe8-106">Член</span><span class="sxs-lookup"><span data-stu-id="acfe8-106">Member</span></span>|<span data-ttu-id="acfe8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="acfe8-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="acfe8-108">Указывает на отсутствие флагов.</span><span class="sxs-lookup"><span data-stu-id="acfe8-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="acfe8-109">Указывает `setLastError` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="acfe8-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="acfe8-110">Указывает `nomangle` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="acfe8-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="acfe8-111">Не используется.</span><span class="sxs-lookup"><span data-stu-id="acfe8-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acfe8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="acfe8-112">Requirements</span></span>  
 <span data-ttu-id="acfe8-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acfe8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acfe8-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="acfe8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acfe8-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acfe8-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="acfe8-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acfe8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfe8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="acfe8-117">See Also</span></span>  
 [<span data-ttu-id="acfe8-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="acfe8-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
