---
title: Структура ASSEMBLY_INFO
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ed65181abab58117d539d23fcfeffe71ac19388
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430574"
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="b66c9-102">Структура ASSEMBLY_INFO</span><span class="sxs-lookup"><span data-stu-id="b66c9-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="b66c9-103">Содержит сведения о сборке, которая зарегистрирована в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="b66c9-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b66c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b66c9-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b66c9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b66c9-105">Members</span></span>  
  
|<span data-ttu-id="b66c9-106">Член</span><span class="sxs-lookup"><span data-stu-id="b66c9-106">Member</span></span>|<span data-ttu-id="b66c9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b66c9-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="b66c9-108">Размер в байтах структуры.</span><span class="sxs-lookup"><span data-stu-id="b66c9-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="b66c9-109">Это поле зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="b66c9-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="b66c9-110">Флаги, указывающие установки сведений о сборке.</span><span class="sxs-lookup"><span data-stu-id="b66c9-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="b66c9-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b66c9-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="b66c9-112">-ASSEMBLYINFO_FLAG_INSTALLED значение, которое указывает, что сборка установлена.</span><span class="sxs-lookup"><span data-stu-id="b66c9-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="b66c9-113">Текущую версию платформы .NET Framework, всегда устанавливает `dwAssemblyFlags` это значение.</span><span class="sxs-lookup"><span data-stu-id="b66c9-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="b66c9-114">-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT значение, которое указывает, что сборка является резидентной полезных данных.</span><span class="sxs-lookup"><span data-stu-id="b66c9-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="b66c9-115">Текущую версию платформы .NET Framework никогда не задает `dwAssemblyFlags` это значение.</span><span class="sxs-lookup"><span data-stu-id="b66c9-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="b66c9-116">Общий размер в килобайтах, файлов, содержащих сборки.</span><span class="sxs-lookup"><span data-stu-id="b66c9-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="b66c9-117">Указатель на буфер строки, содержащий текущий путь к файлу манифеста.</span><span class="sxs-lookup"><span data-stu-id="b66c9-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="b66c9-118">Путь должен заканчиваться символом null.</span><span class="sxs-lookup"><span data-stu-id="b66c9-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="b66c9-119">Число расширенных символов, включая завершающий символ null, `pszCurrentAssemblyPathBuf` содержит.</span><span class="sxs-lookup"><span data-stu-id="b66c9-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b66c9-120">Требования</span><span class="sxs-lookup"><span data-stu-id="b66c9-120">Requirements</span></span>  
 <span data-ttu-id="b66c9-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b66c9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b66c9-122">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b66c9-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b66c9-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b66c9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b66c9-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b66c9-124">See Also</span></span>  
 [<span data-ttu-id="b66c9-125">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="b66c9-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="b66c9-126">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="b66c9-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
