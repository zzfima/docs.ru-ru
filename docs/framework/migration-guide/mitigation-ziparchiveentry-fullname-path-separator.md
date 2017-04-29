---
title: "Устранение рисков: разделитель пути ZipArchiveEntry.FullName | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 747c98e0fd9db95c52531b398aa33161decac294
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Устранение рисков: разделитель пути ZipArchiveEntry.FullName
Начиная с приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], разделитель пути, используемый в свойстве <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=fullName>, изменен: вместо обратной косой черты ("\\"), используемой в предыдущих версиях платформы .NET Framework, теперь используется косая черта ("/").   Объекты <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=fullName> создаются путем вызова одной из перегрузок метода <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>.  
  
## <a name="impact"></a>Последствия  
 Изменение обеспечивает соответствие реализации .NET разделу 4.4.17.1 [спецификации формата ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) и позволяет распаковывать ZIP-архивы в системах, отличных от Windows.  
  
 При распаковке ZIP-файла, созданного приложением, предназначенным для предыдущей версии платформы .NET Framework в операционных системах, отличающихся от Windows, таких как Macintosh, не удается сохранить структуру каталогов. Например, на компьютерах Macintosh создается набор файлов, имя которых объединяет путь к каталогу, вместе со всеми символами обратной косой черты ("\\"), и имя файла. В результате структура каталогов распакованных файлов не сохраняется.  
  
 Влияние этого изменения на ZIP-файлы, которые распаковываются в операционной системе Windows API-интерфейсами в пространстве имен .NET Framework <xref:System.IO>, должно быть минимальным, поскольку эти API могут беспрепятственно обрабатывать как косую черту ("/"), так и обратную косую черту ("\\") в качестве символа разделителя пути.  
  
## <a name="mitigation"></a>Уменьшение  
 Если такое поведение нежелательно, от него можно отказаться, добавив параметр конфигурации в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. Ниже показаны как раздел `<runtime>`, так и параметр отключения функции.  
  
```  
  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
  
```  
  
 Кроме того, в приложениях, предназначенных для предыдущих версий .NET Framework, но выполняемых в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более поздних версиях, можно включить такое поведение, добавив параметр конфигурации в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. Ниже показаны как раздел `<runtime>`, так и параметр включения функции.  
  
```  
  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
  
```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)   
 [Совместимость приложений в 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
