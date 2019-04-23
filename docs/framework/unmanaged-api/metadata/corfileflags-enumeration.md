---
title: Перечисление CorFileFlags
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 076d5de3e9d1925e3a030fee4a06a89862105897
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159618"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="bf4f9-102">Перечисление CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="bf4f9-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="bf4f9-103">Содержит значения, описывающие тип файла, определенного в вызове к [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="bf4f9-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf4f9-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="bf4f9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="bf4f9-105">Members</span></span>  
  
|<span data-ttu-id="bf4f9-106">Член</span><span class="sxs-lookup"><span data-stu-id="bf4f9-106">Member</span></span>|<span data-ttu-id="bf4f9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bf4f9-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="bf4f9-108">Указывает, что файл не является файлом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="bf4f9-109">Указывает, что файл, возможно, файл ресурсов не содержит метаданных.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf4f9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bf4f9-110">Requirements</span></span>  
 <span data-ttu-id="bf4f9-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf4f9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf4f9-112">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bf4f9-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bf4f9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf4f9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4f9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bf4f9-114">See also</span></span>

- [<span data-ttu-id="bf4f9-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="bf4f9-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
