---
title: Перечисление CorFileMapping
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905740"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="7dd6c-102">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="7dd6c-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="7dd6c-103">Содержит значения, описывающие тип сопоставления файлов, которое возвращается из вызова [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7dd6c-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd6c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dd6c-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="7dd6c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7dd6c-105">Members</span></span>  
  
|<span data-ttu-id="7dd6c-106">Член</span><span class="sxs-lookup"><span data-stu-id="7dd6c-106">Member</span></span>|<span data-ttu-id="7dd6c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7dd6c-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="7dd6c-108">Файл сопоставляется как файл данных.</span><span class="sxs-lookup"><span data-stu-id="7dd6c-108">The file is mapped as a data file.</span></span> <span data-ttu-id="7dd6c-109">То есть `SEC_IMAGE` Microsoft Win32 не передан флаг `CreateFileMapping` функции.</span><span class="sxs-lookup"><span data-stu-id="7dd6c-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="7dd6c-110">Сопоставленный файл для выполнения, либо при помощи `LoadLibrary` функции или `CreateFileMapping` функционировать с `SEC_IMAGE` флаг.</span><span class="sxs-lookup"><span data-stu-id="7dd6c-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7dd6c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7dd6c-111">Requirements</span></span>  
 <span data-ttu-id="7dd6c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dd6c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dd6c-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7dd6c-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7dd6c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dd6c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd6c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7dd6c-115">See also</span></span>

- [<span data-ttu-id="7dd6c-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7dd6c-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="7dd6c-117">Метод GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="7dd6c-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
