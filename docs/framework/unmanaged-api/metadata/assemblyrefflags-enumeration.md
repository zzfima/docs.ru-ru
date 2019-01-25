---
title: Перечисление AssemblyRefFlags
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b31df454c49ddccc74a7e877c09efa4f45b69d9e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491798"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="02e1f-102">Перечисление AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="02e1f-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="02e1f-103">Содержит значения, описывающие возможности ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="02e1f-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02e1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02e1f-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="02e1f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="02e1f-105">Members</span></span>  
  
|<span data-ttu-id="02e1f-106">Член</span><span class="sxs-lookup"><span data-stu-id="02e1f-106">Member</span></span>|<span data-ttu-id="02e1f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="02e1f-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="02e1f-108">Указывает, что ссылки на сборку содержит полный, не хэшированный сведений об издателе сборки.</span><span class="sxs-lookup"><span data-stu-id="02e1f-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02e1f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="02e1f-109">Requirements</span></span>  
 <span data-ttu-id="02e1f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02e1f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02e1f-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="02e1f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02e1f-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02e1f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e1f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="02e1f-113">See also</span></span>
- [<span data-ttu-id="02e1f-114">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="02e1f-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="02e1f-115">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="02e1f-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="02e1f-116">Метод DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="02e1f-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
