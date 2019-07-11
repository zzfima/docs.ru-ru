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
ms.openlocfilehash: 944c641c39ddef7add0e9f382dc7d35068668455
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781721"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="11a95-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="11a95-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="11a95-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="11a95-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11a95-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="11a95-105">Участники</span><span class="sxs-lookup"><span data-stu-id="11a95-105">Members</span></span>  
  
|<span data-ttu-id="11a95-106">Член</span><span class="sxs-lookup"><span data-stu-id="11a95-106">Member</span></span>|<span data-ttu-id="11a95-107">Описание</span><span class="sxs-lookup"><span data-stu-id="11a95-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="11a95-108">Указывает, что не указан ни один из ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="11a95-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="11a95-109">Указывает, что ключевое слово в формате ANSI.</span><span class="sxs-lookup"><span data-stu-id="11a95-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="11a95-110">Указывает, что указан Unicode-ключевое слово</span><span class="sxs-lookup"><span data-stu-id="11a95-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="11a95-111">Указывает, что ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="11a95-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="11a95-112">Указывает, что ключевое слово OLE.</span><span class="sxs-lookup"><span data-stu-id="11a95-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="11a95-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="11a95-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11a95-114">Требования</span><span class="sxs-lookup"><span data-stu-id="11a95-114">Requirements</span></span>  
 <span data-ttu-id="11a95-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a95-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a95-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11a95-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11a95-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11a95-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11a95-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a95-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a95-119">См. также</span><span class="sxs-lookup"><span data-stu-id="11a95-119">See also</span></span>

- [<span data-ttu-id="11a95-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="11a95-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
