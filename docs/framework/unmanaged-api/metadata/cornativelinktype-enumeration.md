---
title: Перечисление CorNativeLinkType
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170078"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="0951d-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="0951d-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="0951d-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="0951d-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0951d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0951d-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="0951d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0951d-105">Members</span></span>  
  
|<span data-ttu-id="0951d-106">Член</span><span class="sxs-lookup"><span data-stu-id="0951d-106">Member</span></span>|<span data-ttu-id="0951d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0951d-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="0951d-108">Указывает, что не указан ни один из ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="0951d-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="0951d-109">Указывает, что ключевое слово в формате ANSI.</span><span class="sxs-lookup"><span data-stu-id="0951d-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="0951d-110">Указывает, что указан Unicode-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="0951d-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="0951d-111">Указывает, что ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="0951d-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="0951d-112">Указывает, что ключевое слово OLE.</span><span class="sxs-lookup"><span data-stu-id="0951d-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="0951d-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="0951d-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0951d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0951d-114">Requirements</span></span>  
 <span data-ttu-id="0951d-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0951d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0951d-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0951d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0951d-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0951d-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0951d-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0951d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0951d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0951d-119">See also</span></span>

- [<span data-ttu-id="0951d-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0951d-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
