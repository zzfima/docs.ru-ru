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
ms.openlocfilehash: c315e2ae2753b59b4e277764d27c3fb3388b515c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445416"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="54e57-102">Перечисление CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="54e57-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="54e57-103">Содержит значения, описывающие тип файла, определенного в вызове [IMetaDataAssemblyEmit::D ефинефиле](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="54e57-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54e57-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="54e57-105">Члены</span><span class="sxs-lookup"><span data-stu-id="54e57-105">Members</span></span>  
  
|<span data-ttu-id="54e57-106">Член</span><span class="sxs-lookup"><span data-stu-id="54e57-106">Member</span></span>|<span data-ttu-id="54e57-107">Описание</span><span class="sxs-lookup"><span data-stu-id="54e57-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="54e57-108">Указывает, что файл не является файлом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="54e57-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="54e57-109">Указывает, что файл, возможно, файл ресурсов, не содержит метаданных.</span><span class="sxs-lookup"><span data-stu-id="54e57-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54e57-110">Требования</span><span class="sxs-lookup"><span data-stu-id="54e57-110">Requirements</span></span>  
 <span data-ttu-id="54e57-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54e57-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e57-112">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="54e57-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="54e57-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e57-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e57-114">См. также</span><span class="sxs-lookup"><span data-stu-id="54e57-114">See also</span></span>

- [<span data-ttu-id="54e57-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="54e57-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
