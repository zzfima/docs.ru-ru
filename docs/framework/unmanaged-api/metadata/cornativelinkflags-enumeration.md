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
ms.openlocfilehash: 1362efbf518310240ce665badc93810d1c0b9b89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450192"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="277e0-102">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="277e0-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="277e0-103">Предоставляет значения флагов, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="277e0-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="277e0-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="277e0-105">Члены</span><span class="sxs-lookup"><span data-stu-id="277e0-105">Members</span></span>  
  
|<span data-ttu-id="277e0-106">Член</span><span class="sxs-lookup"><span data-stu-id="277e0-106">Member</span></span>|<span data-ttu-id="277e0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="277e0-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="277e0-108">Указывает, что флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="277e0-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="277e0-109">Указывает ключевое слово `setLastError`.</span><span class="sxs-lookup"><span data-stu-id="277e0-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="277e0-110">Указывает ключевое слово `nomangle`.</span><span class="sxs-lookup"><span data-stu-id="277e0-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="277e0-111">Не используется.</span><span class="sxs-lookup"><span data-stu-id="277e0-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="277e0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="277e0-112">Requirements</span></span>  
 <span data-ttu-id="277e0-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="277e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="277e0-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="277e0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="277e0-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="277e0-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="277e0-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="277e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277e0-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="277e0-117">See also</span></span>

- [<span data-ttu-id="277e0-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="277e0-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
