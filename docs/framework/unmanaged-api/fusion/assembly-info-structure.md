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
ms.openlocfilehash: a43d5e15c02a97ff10a6a5afd439cadebb6b33d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109218"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="ec71a-102">Структура ASSEMBLY_INFO</span><span class="sxs-lookup"><span data-stu-id="ec71a-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="ec71a-103">Содержит сведения о сборке, зарегистрированной в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="ec71a-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec71a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec71a-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="ec71a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ec71a-105">Members</span></span>  
  
|<span data-ttu-id="ec71a-106">Член</span><span class="sxs-lookup"><span data-stu-id="ec71a-106">Member</span></span>|<span data-ttu-id="ec71a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ec71a-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="ec71a-108">Размер структуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="ec71a-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="ec71a-109">Это поле зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="ec71a-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="ec71a-110">Флаги, указывающие сведения об установке сборки.</span><span class="sxs-lookup"><span data-stu-id="ec71a-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="ec71a-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ec71a-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="ec71a-112">— Значение ASSEMBLYINFO_FLAG_INSTALLED, указывающее, что сборка установлена.</span><span class="sxs-lookup"><span data-stu-id="ec71a-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="ec71a-113">Текущая версия .NET Framework всегда задает для `dwAssemblyFlags` это значение.</span><span class="sxs-lookup"><span data-stu-id="ec71a-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="ec71a-114">— Значение ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, которое указывает, что сборка является резидентной полезной нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="ec71a-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="ec71a-115">Текущая версия .NET Framework никогда не задает `dwAssemblyFlags` этому значению.</span><span class="sxs-lookup"><span data-stu-id="ec71a-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="ec71a-116">Общий размер файлов, содержащихся в сборке, в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="ec71a-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="ec71a-117">Указатель на строковый буфер, содержащий текущий путь к файлу манифеста.</span><span class="sxs-lookup"><span data-stu-id="ec71a-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="ec71a-118">Путь должен заканчиваться нулевым символом.</span><span class="sxs-lookup"><span data-stu-id="ec71a-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="ec71a-119">Количество расширенных символов, включая знак завершения null, который `pszCurrentAssemblyPathBuf` содержит.</span><span class="sxs-lookup"><span data-stu-id="ec71a-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec71a-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ec71a-120">Requirements</span></span>  
 <span data-ttu-id="ec71a-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec71a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec71a-122">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ec71a-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ec71a-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec71a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec71a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ec71a-124">See also</span></span>

- [<span data-ttu-id="ec71a-125">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="ec71a-125">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="ec71a-126">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="ec71a-126">Global Assembly Cache</span></span>](../../app-domains/gac.md)
