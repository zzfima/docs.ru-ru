---
title: Структура ASSEMBLYMETADATA
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f0a9b9c149c86b4d9121275aa858dfdc0cdbac7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195167"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="29c6b-102">Структура ASSEMBLYMETADATA</span><span class="sxs-lookup"><span data-stu-id="29c6b-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="29c6b-103">Содержит сведения о сборке, на которую указывает ссылка, включая ее версию и уровень поддержки языковых стандартов, процессоры и операционные системы.</span><span class="sxs-lookup"><span data-stu-id="29c6b-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29c6b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="29c6b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="29c6b-105">Members</span></span>  
  
|<span data-ttu-id="29c6b-106">Член</span><span class="sxs-lookup"><span data-stu-id="29c6b-106">Member</span></span>|<span data-ttu-id="29c6b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="29c6b-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="29c6b-108">Основной номер версии сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="29c6b-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="29c6b-109">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="29c6b-109">This value cannot be zero.</span></span> <span data-ttu-id="29c6b-110">Если все биты `usMajorVersion` задаются, основной номер версии не указан.</span><span class="sxs-lookup"><span data-stu-id="29c6b-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="29c6b-111">Дополнительный номер версии сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="29c6b-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="29c6b-112">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="29c6b-112">This value cannot be zero.</span></span> <span data-ttu-id="29c6b-113">Если все биты `usMinorVersion` задаются, дополнительный номер версии не указан.</span><span class="sxs-lookup"><span data-stu-id="29c6b-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="29c6b-114">Номер построения сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="29c6b-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="29c6b-115">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="29c6b-115">This value cannot be zero.</span></span> <span data-ttu-id="29c6b-116">Если все биты `usBuildNumber` задаются, номер сборки не указан.</span><span class="sxs-lookup"><span data-stu-id="29c6b-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="29c6b-117">Номер редакции сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="29c6b-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="29c6b-118">Это значение не может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="29c6b-118">This value cannot be zero.</span></span> <span data-ttu-id="29c6b-119">Если все биты `usRevisionNumber` задаются, не указан номер редакции.</span><span class="sxs-lookup"><span data-stu-id="29c6b-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="29c6b-120">Список имен языковых стандартов, выполняет существующую спецификацию RFC1766, разделенных точкой с запятой, указав языки, поддерживаемые сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="29c6b-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="29c6b-121">Значение null указывает на независимость от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="29c6b-121">A null value indicates locale independence.</span></span> <span data-ttu-id="29c6b-122">**Примечание.**  В .NET Framework версии 1.0, нельзя указать более одного языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="29c6b-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="29c6b-123">Размер в расширенных символах `szLocale`.</span><span class="sxs-lookup"><span data-stu-id="29c6b-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="29c6b-124">Массив идентификаторов, как определено в заголовке Winnt.h, для типов процессоров, поддерживаемых сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="29c6b-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="29c6b-125">Значение NULL указывает на независимость от процессора.</span><span class="sxs-lookup"><span data-stu-id="29c6b-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="29c6b-126">Длина `rdwProcessor` массива.</span><span class="sxs-lookup"><span data-stu-id="29c6b-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="29c6b-127">Массив [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) экземпляров, задающих операционные системы, поддерживаемые сборкой, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="29c6b-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="29c6b-128">Значение NULL указывает на независимость от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="29c6b-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="29c6b-129">Длина `rOS` массива.</span><span class="sxs-lookup"><span data-stu-id="29c6b-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29c6b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="29c6b-130">Requirements</span></span>  
 <span data-ttu-id="29c6b-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c6b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c6b-132">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="29c6b-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29c6b-133">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29c6b-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="29c6b-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c6b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c6b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="29c6b-135">See also</span></span>

- [<span data-ttu-id="29c6b-136">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="29c6b-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="29c6b-137">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="29c6b-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="29c6b-138">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="29c6b-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
