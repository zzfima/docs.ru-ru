---
title: "Структура ASSEMBLYMETADATA"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLYMETADATA
api_location: mscoree.dll
api_type: COM
f1_keywords: ASSEMBLYMETADATA
helpviewer_keywords: ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5652907abc17868414c554cb5c87b0856d2c5a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="2f290-102">Структура ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="2f290-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="2f290-103">Содержит сведения о ссылочной сборки, включая его версии, уровне поддержки языковых стандартов, процессоры и операционные системы.</span><span class="sxs-lookup"><span data-stu-id="2f290-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f290-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f290-104">Syntax</span></span>  
  
```  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="2f290-105">Члены</span><span class="sxs-lookup"><span data-stu-id="2f290-105">Members</span></span>  
  
|<span data-ttu-id="2f290-106">Член</span><span class="sxs-lookup"><span data-stu-id="2f290-106">Member</span></span>|<span data-ttu-id="2f290-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2f290-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="2f290-108">Основной номер версии сборки.</span><span class="sxs-lookup"><span data-stu-id="2f290-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="2f290-109">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="2f290-109">This value cannot be zero.</span></span> <span data-ttu-id="2f290-110">Если все биты `usMajorVersion` настраиваются, основной номер версии не указан.</span><span class="sxs-lookup"><span data-stu-id="2f290-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="2f290-111">Дополнительный номер версии сборки.</span><span class="sxs-lookup"><span data-stu-id="2f290-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="2f290-112">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="2f290-112">This value cannot be zero.</span></span> <span data-ttu-id="2f290-113">Если все биты `usMinorVersion` настраиваются, дополнительный номер версии не указан.</span><span class="sxs-lookup"><span data-stu-id="2f290-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="2f290-114">Номер построения сборки.</span><span class="sxs-lookup"><span data-stu-id="2f290-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="2f290-115">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="2f290-115">This value cannot be zero.</span></span> <span data-ttu-id="2f290-116">Если все биты `usBuildNumber` настраиваются, номер сборки не указан.</span><span class="sxs-lookup"><span data-stu-id="2f290-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="2f290-117">Номер редакции сборки.</span><span class="sxs-lookup"><span data-stu-id="2f290-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="2f290-118">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="2f290-118">This value cannot be zero.</span></span> <span data-ttu-id="2f290-119">Если все биты `usRevisionNumber` настраиваются, номер редакции не определен.</span><span class="sxs-lookup"><span data-stu-id="2f290-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="2f290-120">Список имен языкового стандарта существующую спецификацию RFC1766, разделенных точкой с запятой, указав языковые стандарты, поддерживаемые сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="2f290-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="2f290-121">Значение null указывает на независимость от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="2f290-121">A null value indicates locale independence.</span></span> <span data-ttu-id="2f290-122">**Примечание:** в .NET Framework версии 1.0, нельзя указать несколько языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="2f290-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="2f290-123">Размер в расширенных символах с `szLocale`.</span><span class="sxs-lookup"><span data-stu-id="2f290-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="2f290-124">Массив идентификаторов, определенный в заголовке Winnt.h, для типов процессоров, поддерживаемых сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="2f290-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="2f290-125">Значение NULL указывает на независимость от процессора.</span><span class="sxs-lookup"><span data-stu-id="2f290-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="2f290-126">Длина `rdwProcessor` массива.</span><span class="sxs-lookup"><span data-stu-id="2f290-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="2f290-127">Массив [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) экземпляров, задающих операционные системы, поддерживаемые сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="2f290-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="2f290-128">Значение NULL указывает на независимость от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2f290-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="2f290-129">Длина `rOS` массива.</span><span class="sxs-lookup"><span data-stu-id="2f290-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f290-130">Требования</span><span class="sxs-lookup"><span data-stu-id="2f290-130">Requirements</span></span>  
 <span data-ttu-id="2f290-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f290-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f290-132">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f290-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f290-133">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f290-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f290-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f290-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f290-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2f290-135">See Also</span></span>  
 [<span data-ttu-id="2f290-136">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="2f290-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="2f290-137">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="2f290-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="2f290-138">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="2f290-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
