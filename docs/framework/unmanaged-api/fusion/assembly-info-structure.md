---
title: "Структура ASSEMBLY_INFO"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="facbb-102">Структура ASSEMBLY_INFO</span><span class="sxs-lookup"><span data-stu-id="facbb-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="facbb-103">Содержит сведения о сборке, которая зарегистрирована в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="facbb-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="facbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="facbb-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="facbb-105">Члены</span><span class="sxs-lookup"><span data-stu-id="facbb-105">Members</span></span>  
  
|<span data-ttu-id="facbb-106">Член</span><span class="sxs-lookup"><span data-stu-id="facbb-106">Member</span></span>|<span data-ttu-id="facbb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="facbb-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="facbb-108">Размер в байтах структуры.</span><span class="sxs-lookup"><span data-stu-id="facbb-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="facbb-109">Это поле зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="facbb-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="facbb-110">Флаги, указывающие установки сведений о сборке.</span><span class="sxs-lookup"><span data-stu-id="facbb-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="facbb-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="facbb-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="facbb-112">-ASSEMBLYINFO_FLAG_INSTALLED значение, которое указывает, что сборка установлена.</span><span class="sxs-lookup"><span data-stu-id="facbb-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="facbb-113">Текущую версию платформы .NET Framework, всегда устанавливает `dwAssemblyFlags` это значение.</span><span class="sxs-lookup"><span data-stu-id="facbb-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="facbb-114">-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT значение, которое указывает, что сборка является резидентной полезных данных.</span><span class="sxs-lookup"><span data-stu-id="facbb-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="facbb-115">Текущую версию платформы .NET Framework никогда не задает `dwAssemblyFlags` это значение.</span><span class="sxs-lookup"><span data-stu-id="facbb-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="facbb-116">Общий размер в килобайтах, файлов, содержащих сборки.</span><span class="sxs-lookup"><span data-stu-id="facbb-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="facbb-117">Указатель на буфер строки, содержащий текущий путь к файлу манифеста.</span><span class="sxs-lookup"><span data-stu-id="facbb-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="facbb-118">Путь должен заканчиваться символом null.</span><span class="sxs-lookup"><span data-stu-id="facbb-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="facbb-119">Число расширенных символов, включая завершающий символ null, `pszCurrentAssemblyPathBuf` содержит.</span><span class="sxs-lookup"><span data-stu-id="facbb-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="facbb-120">Требования</span><span class="sxs-lookup"><span data-stu-id="facbb-120">Requirements</span></span>  
 <span data-ttu-id="facbb-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="facbb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facbb-122">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="facbb-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="facbb-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facbb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facbb-124">См. также</span><span class="sxs-lookup"><span data-stu-id="facbb-124">See Also</span></span>  
 [<span data-ttu-id="facbb-125">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="facbb-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="facbb-126">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="facbb-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
