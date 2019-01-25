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
ms.openlocfilehash: 0f946179fc31adebc8e8fc67c394e0b55a876f49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641334"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="05f02-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="05f02-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="05f02-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="05f02-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05f02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05f02-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="05f02-105">Участники</span><span class="sxs-lookup"><span data-stu-id="05f02-105">Members</span></span>  
  
|<span data-ttu-id="05f02-106">Член</span><span class="sxs-lookup"><span data-stu-id="05f02-106">Member</span></span>|<span data-ttu-id="05f02-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="05f02-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="05f02-108">Указывает, что не указан ни один из ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="05f02-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="05f02-109">Указывает, что ключевое слово в формате ANSI.</span><span class="sxs-lookup"><span data-stu-id="05f02-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="05f02-110">Указывает, что указан Unicode-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="05f02-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="05f02-111">Указывает, что ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="05f02-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="05f02-112">Указывает, что ключевое слово OLE.</span><span class="sxs-lookup"><span data-stu-id="05f02-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="05f02-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="05f02-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05f02-114">Требования</span><span class="sxs-lookup"><span data-stu-id="05f02-114">Requirements</span></span>  
 <span data-ttu-id="05f02-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05f02-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05f02-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05f02-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05f02-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05f02-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05f02-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05f02-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f02-119">См. также</span><span class="sxs-lookup"><span data-stu-id="05f02-119">See also</span></span>
- [<span data-ttu-id="05f02-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="05f02-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
