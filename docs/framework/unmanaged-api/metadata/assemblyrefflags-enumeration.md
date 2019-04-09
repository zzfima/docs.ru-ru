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
ms.openlocfilehash: bc98b2421d23ffd6dfb716a8cc782b46a9d59ce0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128900"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="dddeb-102">Перечисление AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="dddeb-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="dddeb-103">Содержит значения, описывающие возможности ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="dddeb-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dddeb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dddeb-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="dddeb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dddeb-105">Members</span></span>  
  
|<span data-ttu-id="dddeb-106">Член</span><span class="sxs-lookup"><span data-stu-id="dddeb-106">Member</span></span>|<span data-ttu-id="dddeb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dddeb-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="dddeb-108">Указывает, что ссылки на сборку содержит полный, не хэшированный сведений об издателе сборки.</span><span class="sxs-lookup"><span data-stu-id="dddeb-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dddeb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dddeb-109">Requirements</span></span>  
 <span data-ttu-id="dddeb-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dddeb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dddeb-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dddeb-111">**Header:** Cor.h</span></span>  
  
 **<span data-ttu-id="dddeb-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dddeb-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dddeb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dddeb-113">See also</span></span>

- [<span data-ttu-id="dddeb-114">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="dddeb-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="dddeb-115">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="dddeb-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="dddeb-116">Метод DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="dddeb-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
