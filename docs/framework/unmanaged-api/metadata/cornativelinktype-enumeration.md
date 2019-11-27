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
ms.openlocfilehash: 718e41e16c07265d8a36b8f6124d99cd3490f7be
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436618"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="5618a-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="5618a-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="5618a-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="5618a-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5618a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5618a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5618a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="5618a-105">Members</span></span>  
  
|<span data-ttu-id="5618a-106">Член</span><span class="sxs-lookup"><span data-stu-id="5618a-106">Member</span></span>|<span data-ttu-id="5618a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5618a-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="5618a-108">Указывает, что ни одно из ключевых слов не указано.</span><span class="sxs-lookup"><span data-stu-id="5618a-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="5618a-109">Указывает, что указано ключевое слово ANSI.</span><span class="sxs-lookup"><span data-stu-id="5618a-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="5618a-110">Указывает, что указано ключевое слово Юникода</span><span class="sxs-lookup"><span data-stu-id="5618a-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="5618a-111">Указывает, что указано ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="5618a-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="5618a-112">Указывает, что указано ключевое слово OLE.</span><span class="sxs-lookup"><span data-stu-id="5618a-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="5618a-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="5618a-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5618a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5618a-114">Requirements</span></span>  
 <span data-ttu-id="5618a-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5618a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5618a-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5618a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5618a-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5618a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5618a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5618a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5618a-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="5618a-119">See also</span></span>

- [<span data-ttu-id="5618a-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="5618a-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
