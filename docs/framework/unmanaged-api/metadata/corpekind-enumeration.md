---
title: Перечисление CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5869eb16bd768d58a6f27a83f2d8d51914a8aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443119"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="3c51c-102">Перечисление CorPEKind</span><span class="sxs-lookup"><span data-stu-id="3c51c-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="3c51c-103">Содержит значения, описывающие переносимый исполняемый (PE) файл, возвращенный из вызова [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="3c51c-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c51c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c51c-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="3c51c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3c51c-105">Members</span></span>  
  
|<span data-ttu-id="3c51c-106">Член</span><span class="sxs-lookup"><span data-stu-id="3c51c-106">Member</span></span>|<span data-ttu-id="3c51c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3c51c-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="3c51c-108">Указывает, что это не PE-файл.</span><span class="sxs-lookup"><span data-stu-id="3c51c-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="3c51c-109">Указывает, что этот PE-файл содержит только управляемый код.</span><span class="sxs-lookup"><span data-stu-id="3c51c-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="3c51c-110">Указывает, что этот PE-файл осуществляет вызовы в Win32.</span><span class="sxs-lookup"><span data-stu-id="3c51c-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="3c51c-111">Указывает, что этот PE-файл будет выполняться на 64-разрядной платформе.</span><span class="sxs-lookup"><span data-stu-id="3c51c-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="3c51c-112">Указывает, что этот PE-файл является машинного кода.</span><span class="sxs-lookup"><span data-stu-id="3c51c-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="3c51c-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="3c51c-113">pe32BitPreferred</span></span>|<span data-ttu-id="3c51c-114">Указывает, что этот PE-файл независимый от платформы и является предпочтительным для загрузки в 32-разрядной среде.</span><span class="sxs-lookup"><span data-stu-id="3c51c-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c51c-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c51c-115">Remarks</span></span>  
 <span data-ttu-id="3c51c-116">Эти значения можно использовать в побитовых сочетаниях.</span><span class="sxs-lookup"><span data-stu-id="3c51c-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c51c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="3c51c-117">Requirements</span></span>  
 <span data-ttu-id="3c51c-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c51c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c51c-119">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3c51c-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3c51c-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c51c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c51c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3c51c-121">See Also</span></span>  
 [<span data-ttu-id="3c51c-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="3c51c-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
