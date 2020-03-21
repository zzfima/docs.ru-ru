---
title: Структура COR_NATIVE_LINK
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: 812b70a594b5aa933f52d36f32d96d712267ecf4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177959"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="e04b7-102">Структура COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="e04b7-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="e04b7-103">Содержит сведения, используемые для связи с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="e04b7-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e04b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e04b7-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="e04b7-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e04b7-105">Members</span></span>  
  
|<span data-ttu-id="e04b7-106">Участник</span><span class="sxs-lookup"><span data-stu-id="e04b7-106">Member</span></span>|<span data-ttu-id="e04b7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e04b7-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="e04b7-108">Тип, который будет связан в родном коде.</span><span class="sxs-lookup"><span data-stu-id="e04b7-108">The type to be linked in native code.</span></span> <span data-ttu-id="e04b7-109">Это значение является одним из значений [CorNativeLinkType.](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="e04b7-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="e04b7-110">Флаги, используемые связующим при связке родного кода.</span><span class="sxs-lookup"><span data-stu-id="e04b7-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="e04b7-111">Это значение является одним из значений [CorNativeLinkFlags.](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="e04b7-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="e04b7-112">Токен метаданных MemberRef, представляющий точку входа.</span><span class="sxs-lookup"><span data-stu-id="e04b7-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="e04b7-113">Формат — `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="e04b7-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e04b7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e04b7-114">Requirements</span></span>  
 <span data-ttu-id="e04b7-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e04b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e04b7-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e04b7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e04b7-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e04b7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e04b7-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e04b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04b7-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e04b7-119">See also</span></span>

- [<span data-ttu-id="e04b7-120">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="e04b7-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="e04b7-121">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="e04b7-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="e04b7-122">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="e04b7-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
