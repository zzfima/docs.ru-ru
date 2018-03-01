---
title: "Перечисление CorFileMapping"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5abde0d34baecf12628c9c6c99f04d6d81dd62fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="3b1de-102">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="3b1de-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="3b1de-103">Содержит значения, описывающие тип сопоставления файлов, которое возвращается из вызова [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3b1de-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b1de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b1de-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="3b1de-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3b1de-105">Members</span></span>  
  
|<span data-ttu-id="3b1de-106">Член</span><span class="sxs-lookup"><span data-stu-id="3b1de-106">Member</span></span>|<span data-ttu-id="3b1de-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="3b1de-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="3b1de-108">Файл сопоставлен как файл данных.</span><span class="sxs-lookup"><span data-stu-id="3b1de-108">The file is mapped as a data file.</span></span> <span data-ttu-id="3b1de-109">То есть `SEC_IMAGE` флаг не был передан в Microsoft Win32 `CreateFileMapping` функции.</span><span class="sxs-lookup"><span data-stu-id="3b1de-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="3b1de-110">Сопоставленный файл для выполнения, с помощью `LoadLibrary` функции или `CreateFileMapping` функционировать с `SEC_IMAGE` флаг.</span><span class="sxs-lookup"><span data-stu-id="3b1de-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b1de-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3b1de-111">Requirements</span></span>  
 <span data-ttu-id="3b1de-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b1de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b1de-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3b1de-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3b1de-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b1de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b1de-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3b1de-115">See Also</span></span>  
 [<span data-ttu-id="3b1de-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="3b1de-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="3b1de-117">Метод GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="3b1de-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
