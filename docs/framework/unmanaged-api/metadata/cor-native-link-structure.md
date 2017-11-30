---
title: "Структура COR_NATIVE_LINK"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_NATIVE_LINK
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_NATIVE_LINK
helpviewer_keywords: COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e27b66fce8a78ef0feb7ed10e77cc51fc1fe83c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cornativelink-structure"></a><span data-ttu-id="fb7dc-102">Структура COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="fb7dc-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="fb7dc-103">Содержит сведения, используемые для связи с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="fb7dc-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb7dc-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="fb7dc-105">Члены</span><span class="sxs-lookup"><span data-stu-id="fb7dc-105">Members</span></span>  
  
|<span data-ttu-id="fb7dc-106">Член</span><span class="sxs-lookup"><span data-stu-id="fb7dc-106">Member</span></span>|<span data-ttu-id="fb7dc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fb7dc-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="fb7dc-108">Тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="fb7dc-108">The type to be linked in native code.</span></span> <span data-ttu-id="fb7dc-109">Это значение является одним из [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="fb7dc-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="fb7dc-110">Флаги, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="fb7dc-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="fb7dc-111">Это значение является одним из [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="fb7dc-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="fb7dc-112">Токен метаданных MemberRef, представляющий точку входа.</span><span class="sxs-lookup"><span data-stu-id="fb7dc-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="fb7dc-113">Недопустимый формат `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="fb7dc-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb7dc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fb7dc-114">Requirements</span></span>  
 <span data-ttu-id="fb7dc-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb7dc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7dc-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb7dc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb7dc-117">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb7dc-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb7dc-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7dc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7dc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fb7dc-119">See Also</span></span>  
 [<span data-ttu-id="fb7dc-120">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="fb7dc-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="fb7dc-121">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="fb7dc-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="fb7dc-122">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="fb7dc-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
