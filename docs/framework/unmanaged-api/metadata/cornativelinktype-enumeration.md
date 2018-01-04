---
title: "Перечисление CorNativeLinkType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkType
helpviewer_keywords: CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f19a4366958249881c1f4c33919f239f33c21b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="0fab0-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="0fab0-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="0fab0-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="0fab0-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fab0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fab0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0fab0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0fab0-105">Members</span></span>  
  
|<span data-ttu-id="0fab0-106">Член</span><span class="sxs-lookup"><span data-stu-id="0fab0-106">Member</span></span>|<span data-ttu-id="0fab0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0fab0-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="0fab0-108">Указывает, что не указан ни один из ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="0fab0-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="0fab0-109">Указывает, что указано ключевое слово в формате ANSI.</span><span class="sxs-lookup"><span data-stu-id="0fab0-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="0fab0-110">Указывает, что указано Unicode-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="0fab0-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="0fab0-111">Указывает, что задано ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="0fab0-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="0fab0-112">Указывает, что указано ключевое слово в формате OLE.</span><span class="sxs-lookup"><span data-stu-id="0fab0-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="0fab0-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="0fab0-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fab0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0fab0-114">Requirements</span></span>  
 <span data-ttu-id="0fab0-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fab0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fab0-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0fab0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fab0-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0fab0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0fab0-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fab0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fab0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0fab0-119">See Also</span></span>  
 [<span data-ttu-id="0fab0-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0fab0-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
