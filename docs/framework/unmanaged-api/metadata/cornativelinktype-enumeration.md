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
ms.openlocfilehash: 0b613ebacdff82a29fdbc3f4caa0f2b8bb5d3f6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176166"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="422a6-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="422a6-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="422a6-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="422a6-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="422a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="422a6-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="422a6-105">Члены</span><span class="sxs-lookup"><span data-stu-id="422a6-105">Members</span></span>  
  
|<span data-ttu-id="422a6-106">Участник</span><span class="sxs-lookup"><span data-stu-id="422a6-106">Member</span></span>|<span data-ttu-id="422a6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="422a6-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="422a6-108">Указывает, что ни одно из ключевых слов не указано.</span><span class="sxs-lookup"><span data-stu-id="422a6-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="422a6-109">Указывается, что указанное ключевое слово ANSI.</span><span class="sxs-lookup"><span data-stu-id="422a6-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="422a6-110">Означает, что указанное ключевое слово Unicode</span><span class="sxs-lookup"><span data-stu-id="422a6-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="422a6-111">Указывает, что указано ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="422a6-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="422a6-112">Указывается, что указанное ключевое слово OLE.</span><span class="sxs-lookup"><span data-stu-id="422a6-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="422a6-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="422a6-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="422a6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="422a6-114">Requirements</span></span>  
 <span data-ttu-id="422a6-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="422a6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="422a6-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="422a6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="422a6-117">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="422a6-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="422a6-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="422a6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422a6-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="422a6-119">See also</span></span>

- [<span data-ttu-id="422a6-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="422a6-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
