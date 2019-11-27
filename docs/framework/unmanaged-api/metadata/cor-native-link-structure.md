---
title: COR_NATIVE_LINK Structure
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
ms.openlocfilehash: d03c22c455f0e44ce32d4593d9eee50ceef94a22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443957"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="dd99d-102">COR_NATIVE_LINK Structure</span><span class="sxs-lookup"><span data-stu-id="dd99d-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="dd99d-103">Содержит сведения, используемые для связи с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="dd99d-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd99d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd99d-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="dd99d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="dd99d-105">Members</span></span>  
  
|<span data-ttu-id="dd99d-106">Член</span><span class="sxs-lookup"><span data-stu-id="dd99d-106">Member</span></span>|<span data-ttu-id="dd99d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dd99d-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="dd99d-108">Тип, который должен быть связан в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="dd99d-108">The type to be linked in native code.</span></span> <span data-ttu-id="dd99d-109">Это значение является одним из значений [корнативелинктипе](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="dd99d-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="dd99d-110">Флаги, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="dd99d-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="dd99d-111">Это значение является одним из значений [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="dd99d-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="dd99d-112">Токен метаданных MemberRef, представляющий точку входа.</span><span class="sxs-lookup"><span data-stu-id="dd99d-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="dd99d-113">Формат `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="dd99d-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd99d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="dd99d-114">Requirements</span></span>  
 <span data-ttu-id="dd99d-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd99d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd99d-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="dd99d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd99d-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dd99d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd99d-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd99d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd99d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dd99d-119">See also</span></span>

- [<span data-ttu-id="dd99d-120">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="dd99d-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="dd99d-121">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="dd99d-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="dd99d-122">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="dd99d-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
