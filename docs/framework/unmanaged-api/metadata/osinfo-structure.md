---
title: Структура OSINFO
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aba49fb4a60b2e471c541a8d8531a1cbc8627f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775204"
---
# <a name="osinfo-structure"></a><span data-ttu-id="525bb-102">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="525bb-102">OSINFO Structure</span></span>
<span data-ttu-id="525bb-103">Содержит сведения об операционной системе для сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="525bb-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="525bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="525bb-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="525bb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="525bb-105">Members</span></span>  
  
|<span data-ttu-id="525bb-106">Член</span><span class="sxs-lookup"><span data-stu-id="525bb-106">Member</span></span>|<span data-ttu-id="525bb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="525bb-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="525bb-108">Одно из значений идентификатора, определенных с помощью функции платформы Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="525bb-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="525bb-109">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="525bb-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="525bb-110">-VER_PLATFORM_WIN32s, или 0x0000, чтобы указать Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="525bb-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="525bb-111">-VER_PLATFORM_WIN32_WINDOWS, или 0x0001, чтобы указать Windows 95, Windows 98 или операционных систем, происходящий из них.</span><span class="sxs-lookup"><span data-stu-id="525bb-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="525bb-112">-VER_PLATFORM_WIN32_NT, или 0x0010, чтобы указать Windows NT или операционных систем, производных от него.</span><span class="sxs-lookup"><span data-stu-id="525bb-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="525bb-113">Основной номер версии операционной системы, или значение NULL для указания любой версии.</span><span class="sxs-lookup"><span data-stu-id="525bb-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="525bb-114">Дополнительный номер версии операционной системы, или значение NULL для указания любой версии.</span><span class="sxs-lookup"><span data-stu-id="525bb-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="525bb-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="525bb-115">Remarks</span></span>  
 <span data-ttu-id="525bb-116">`OSINFO` на основе `OSVERSIONINFOEX` структура и используется в вызовах функции платформы Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="525bb-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="525bb-117">Эта структура используется структура ASSEMBLYMETADATA для указания поддержки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="525bb-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="525bb-118">Требования</span><span class="sxs-lookup"><span data-stu-id="525bb-118">Requirements</span></span>  
 <span data-ttu-id="525bb-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="525bb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="525bb-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="525bb-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="525bb-121">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="525bb-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="525bb-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="525bb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="525bb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="525bb-123">See also</span></span>

- [<span data-ttu-id="525bb-124">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="525bb-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="525bb-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="525bb-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
