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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175230"
---
# <a name="osinfo-structure"></a><span data-ttu-id="e7e46-102">Структура OSINFO</span><span class="sxs-lookup"><span data-stu-id="e7e46-102">OSINFO Structure</span></span>
<span data-ttu-id="e7e46-103">Содержит подробную информацию об операционной системе для сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="e7e46-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7e46-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e7e46-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e7e46-105">Members</span></span>  
  
|<span data-ttu-id="e7e46-106">Участник</span><span class="sxs-lookup"><span data-stu-id="e7e46-106">Member</span></span>|<span data-ttu-id="e7e46-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e7e46-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="e7e46-108">Одно из значений идентификатора, `GetVersionEx`определяемое функцией платформы Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e7e46-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="e7e46-109">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="e7e46-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="e7e46-110">- VER_PLATFORM_WIN32s, или 0x0000, чтобы указать Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="e7e46-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="e7e46-111">- VER_PLATFORM_WIN32_WINDOWS, или 0x0001, чтобы указать Windows 95, Windows 98, или операционные системы произошли от них.</span><span class="sxs-lookup"><span data-stu-id="e7e46-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="e7e46-112">- VER_PLATFORM_WIN32_NT, или 0x0002, чтобы указать Windows NT или операционные системы произошли от него.</span><span class="sxs-lookup"><span data-stu-id="e7e46-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="e7e46-113">Основная версия операционной системы, или значение NULL для обозначения любой версии.</span><span class="sxs-lookup"><span data-stu-id="e7e46-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="e7e46-114">Незначительная версия операционной системы, или значение NULL для обозначения любой версии.</span><span class="sxs-lookup"><span data-stu-id="e7e46-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e46-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7e46-115">Remarks</span></span>  
 <span data-ttu-id="e7e46-116">`OSINFO`основанна на `OSVERSIONINFOEX` структуре, которая используется при вызовах к функции `GetVersionEx`платформы Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e7e46-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="e7e46-117">Эта структура используется структурой ASSEMBLYMETADATA для обозначения поддержки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e7e46-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e46-118">Требования</span><span class="sxs-lookup"><span data-stu-id="e7e46-118">Requirements</span></span>  
 <span data-ttu-id="e7e46-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e46-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e46-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e7e46-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7e46-121">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7e46-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7e46-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e46-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e46-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e7e46-123">See also</span></span>

- [<span data-ttu-id="e7e46-124">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="e7e46-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="e7e46-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="e7e46-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
