---
title: 'Устранение рисков: разделитель пути ZipArchiveEntry.FullName'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3940cf8d1ebda668925a5c461b84a8bc61550476
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="6a99b-102">Устранение рисков: разделитель пути ZipArchiveEntry.FullName</span><span class="sxs-lookup"><span data-stu-id="6a99b-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="6a99b-103">Начиная с приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], изменен разделитель пути для свойства <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>: вместо обратной косой черты ("\\"), используемой в предыдущих версиях платформы .NET Framework, теперь используется прямая косая черта ("/").</span><span class="sxs-lookup"><span data-stu-id="6a99b-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="6a99b-104">Объекты <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> создаются путем вызова одной из перегрузок метода <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6a99b-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="6a99b-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="6a99b-105">Impact</span></span>  
 <span data-ttu-id="6a99b-106">Изменение обеспечивает соответствие реализации .NET разделу 4.4.17.1 [спецификации формата ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) и позволяет распаковывать ZIP-архивы в системах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="6a99b-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="6a99b-107">При распаковке ZIP-файла, созданного приложением, предназначенным для предыдущей версии платформы .NET Framework в операционных системах, отличающихся от Windows, таких как Macintosh, не удается сохранить структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="6a99b-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="6a99b-108">Например, на компьютерах Macintosh создается набор файлов, имя которых объединяет путь к каталогу, вместе со всеми символами обратной косой черты ("\\"), и имя файла.</span><span class="sxs-lookup"><span data-stu-id="6a99b-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="6a99b-109">В результате структура каталогов распакованных файлов не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="6a99b-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="6a99b-110">Влияние этого изменения на ZIP-файлы, которые распаковываются в операционной системе Windows API-интерфейсами из пространства имен .NET Framework <xref:System.IO>, должно быть минимальным, поскольку эти API без проблем принимают в качестве символа разделителя пути как косую черту ("/"), так и обратную косую черту ("\\") .</span><span class="sxs-lookup"><span data-stu-id="6a99b-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="6a99b-111">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="6a99b-111">Mitigation</span></span>  
 <span data-ttu-id="6a99b-112">Если такое поведение нежелательно, от него можно отказаться, добавив параметр конфигурации в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="6a99b-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="6a99b-113">Ниже показаны как раздел `<runtime>`, так и параметр отключения функции.</span><span class="sxs-lookup"><span data-stu-id="6a99b-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="6a99b-114">Кроме того, в приложениях, предназначенных для предыдущих версий .NET Framework, но выполняемых в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более поздних версиях, можно включить такое поведение, добавив параметр конфигурации в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="6a99b-114">In addition, apps that target previous versions of the .NET Framework but are running on the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="6a99b-115">Ниже показаны как раздел `<runtime>`, так и параметр включения функции.</span><span class="sxs-lookup"><span data-stu-id="6a99b-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a99b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6a99b-116">See Also</span></span>  
 [<span data-ttu-id="6a99b-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="6a99b-117">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)  
 [<span data-ttu-id="6a99b-118">Совместимость приложений в 4.6.1</span><span class="sxs-lookup"><span data-stu-id="6a99b-118">Application Compatibility in 4.6.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
