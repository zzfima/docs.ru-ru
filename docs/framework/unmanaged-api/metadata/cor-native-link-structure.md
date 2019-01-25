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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08d27eb834c1a9a3a5d163bb2d3054f599ae1669
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719564"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="b426a-102">Структура COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="b426a-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="b426a-103">Содержит сведения, используемые для связи с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="b426a-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b426a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b426a-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="b426a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b426a-105">Members</span></span>  
  
|<span data-ttu-id="b426a-106">Член</span><span class="sxs-lookup"><span data-stu-id="b426a-106">Member</span></span>|<span data-ttu-id="b426a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b426a-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="b426a-108">Тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="b426a-108">The type to be linked in native code.</span></span> <span data-ttu-id="b426a-109">Это значение является одним из [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="b426a-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="b426a-110">Флаги, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="b426a-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="b426a-111">Это значение является одним из [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="b426a-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="b426a-112">Маркер метаданных MemberRef, представляющий точку входа.</span><span class="sxs-lookup"><span data-stu-id="b426a-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="b426a-113">Формат `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="b426a-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b426a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b426a-114">Requirements</span></span>  
 <span data-ttu-id="b426a-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b426a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b426a-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b426a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b426a-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b426a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b426a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b426a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b426a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b426a-119">See also</span></span>
- [<span data-ttu-id="b426a-120">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="b426a-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="b426a-121">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="b426a-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="b426a-122">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="b426a-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
