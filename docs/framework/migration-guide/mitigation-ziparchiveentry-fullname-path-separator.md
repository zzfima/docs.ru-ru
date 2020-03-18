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
ms.openlocfilehash: 021d22e90ba39a4d01cf7d64588fab2d724b6640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457730"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Устранение рисков: разделитель пути ZipArchiveEntry.FullName
Начиная с приложений, предназначенных для .NET Framework 4.6.1, изменен разделитель пути для свойства <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>: вместо обратной косой черты ("\\"), используемой в предыдущих версиях платформы .NET Framework, теперь используется прямая косая черта ("/").   Объекты <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> создаются путем вызова одной из перегрузок метода <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.  
  
## <a name="impact"></a>Последствия  
 Изменение обеспечивает соответствие реализации .NET разделу 4.4.17.1 [спецификации формата ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) и позволяет распаковывать ZIP-архивы в системах, отличных от Windows.  
  
 При распаковке ZIP-файла, созданного приложением, предназначенным для предыдущей версии платформы .NET Framework в операционных системах, отличающихся от Windows, таких как Macintosh, не удается сохранить структуру каталогов. Например, на компьютерах Macintosh создается набор файлов, имя которых объединяет путь к каталогу, вместе со всеми символами обратной косой черты ("\\"), и имя файла. В результате структура каталогов распакованных файлов не сохраняется.  
  
 Влияние этого изменения на ZIP-файлы, которые распаковываются в операционной системе Windows API-интерфейсами из пространства имен .NET Framework <xref:System.IO>, должно быть минимальным, поскольку эти API без проблем принимают в качестве символа разделителя пути как косую черту ("/"), так и обратную косую черту ("\\") .  
  
## <a name="mitigation"></a>Меры по снижению риска  
 Если такое поведение нежелательно, от него можно отказаться, добавив параметр конфигурации в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. Ниже показаны как раздел `<runtime>`, так и параметр отключения функции.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 Кроме того, в приложениях, предназначенных для предыдущих версий .NET Framework, но выполняемых в .NET Framework 4.6.1 и более поздних версиях, можно включить такое поведение, добавив параметр конфигурации в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. Ниже показаны как раздел `<runtime>`, так и параметр включения функции.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Изменение целевой платформы](retargeting-changes-in-the-net-framework-4-6-1.md)
- [Совместимость приложений](application-compatibility.md)
