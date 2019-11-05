---
title: Средство анализа композиции (Mefx)
ms.date: 03/30/2017
helpviewer_keywords:
- Composition Analysis Tool [MEF]
- MEF, Composition Analysis Tool
- Mefx [MEF], Composition Analysis Tool
ms.assetid: c48a7f93-83bb-4a06-aea0-d8e7bd1502ad
ms.openlocfilehash: bb2748b16a16d7d01b076402889829f5b31a1912
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126372"
---
# <a name="composition-analysis-tool-mefx"></a>Средство анализа композиции (Mefx)
Средство анализа композиции (Mefx) — это приложение командной строки, анализирующее файлы библиотеки (.dll) и приложений (.exe) с частями Managed Extensibility Framework (MEF). Основное назначение Mefx — предоставить разработчикам способ диагностики ошибок композиции в приложениях MEF, не добавляя громоздкий код трассировки в само приложение. Это средство также помогает понять части из сторонней библиотеки. В этом разделе описывается использование Mefx, содержится справочная информация по его синтаксису.  
  
<a name="getting_mefx"></a>   
## <a name="getting-mefx"></a>Получение Mefx  
 Средство Mefx доступно в GitHub по следующей ссылке: [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0). Просто загрузите и распакуйте средство.  
  
<a name="basic_syntax"></a>   
## <a name="basic-syntax"></a>Базовый синтаксис  
 Mefx вызывается из командной строки в следующем формате.  
  
```console
mefx [files and directories] [action] [options]  
```  
  
 Первый набор аргументов обозначает файлы и каталоги, из которых требуется загрузить части для анализа. Укажите файл с переключателем `/file:` и каталог с переключателем `/directory:` . Можно указать несколько файлов или каталогов, как показано в следующем примере.  
  
```console  
mefx /file:MyAddIn.dll /directory:Program\AddIns [action...]  
```  
  
> [!NOTE]
> Каждый файл .dll или .exe следует загружать только один раз. Если файл загружается несколько раз, средство может вернуть неправильные данные.  
  
 После списка файлов и каталогов необходимо указать команду и параметры для этой команды.  
  
<a name="listing_available_parts"></a>   
## <a name="listing-available-parts"></a>Составление списка доступных частей  
 Используйте действие `/parts` , чтобы составить список всех частей, объявленных в загруженных файлах. Результатом является простой список имен частей.  
  
```console
mefx /file:MyAddIn.dll /parts  
MyAddIn.AddIn  
MyAddIn.MemberPart  
```  
  
 Для получения дополнительных сведений о частях воспользуйтесь параметром `/verbose` . Это позволит вывести дополнительные сведения обо всех доступных частях. Для получения дополнительной информации об определенной части воспользуйтесь действием `/type` , а не `/parts`.  
  
```console  
mefx /file:MyAddIn.dll /type:MyAddIn.AddIn /verbose  
[Part] MyAddIn.MemberPart from: AssemblyCatalog (Assembly=" MyAddIn, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] MyAddIn.MemberPart (ContractName=" MyAddIn.MemberPart")  
```  
  
<a name="listing_imports_and_exports"></a>   
## <a name="listing-imports-and-exports"></a>Составление списка импортируемых и экспортируемых элементов  
 Действия `/imports` и `/exports` позволяют перечислить все импортируемые и экспортируемые части соответственно. Также можно составить список частей, импортирующих или экспортирующих определенный тип, воспользовавшись действиями `/importers` или `/exporters` .  
  
```console  
mefx /file:MyAddIn.dll /importers:MyAddin.MemberPart  
MyAddin.AddIn  
```  
  
 К этим действиям также можно применить параметр `/verbose` .  
  
<a name="finding_rejected_parts"></a>   
## <a name="finding-rejected-parts"></a>Поиск отклоненных частей  
 После загрузки доступных частей Mefx с помощью модуля композиции MEF составляет из них композицию. Части, которые не удается включить в композицию, называются *отклоненными*. Чтобы составить список всех отклоненных частей, воспользуйтесь действием `/rejected` .  
  
 Для печати подробных сведений об отклоненных частях можно воспользоваться параметром `/verbose` и действием `/rejected` . В следующем примере библиотека DLL `ClassLibrary1` содержит часть `AddIn` , которая импортирует части `MemberPart` и `ChainOne` . `ChainOne` импортирует `ChainTwo`, но `ChainTwo` не существует. Это означает, что `ChainOne` отклоняется, в результате чего отклоняется также и часть `AddIn` .  
  
```console  
mefx /file:ClassLibrary1.dll /rejected /verbose  
```  
  
 Ниже показаны полные выходные данные предыдущей команды.  
  
```output
[Part] ClassLibrary1.AddIn from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] ClassLibrary1.AddIn (ContractName="ClassLibrary1.AddIn")  
  [Import] ClassLibrary1.AddIn.memberPart (ContractName="ClassLibrary1.MemberPart")  
    [SatisfiedBy] ClassLibrary1.MemberPart (ContractName="ClassLibrary1.MemberPart") from: ClassLibrary1.MemberPart from: AssemblyCatalog (Assembly="ClassLibrar  
y1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Import] ClassLibrary1.AddIn.chain (ContractName="ClassLibrary1.ChainOne")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainOne") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainOne".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
    [Unsuitable] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
from: ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
      [Because] PartDefinitionIsRejected, The part providing the export is rejected because of other issues.  
  
[Part] ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Primary Rejection]  
  [Export] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
  [Import] ClassLibrary1.ChainOne.chain (ContractName="ClassLibrary1.ChainTwo")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainTwo") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainTwo".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
```  
  
 Интересные сведения содержатся в результатах `[Exception]` и `[Unsuitable]` . Результат `[Exception]` предоставляет сведения о том, почему часть была отклонена. Результат `[Unsuitable]` показывает, почему подходящую по остальным параметрам часть невозможно использовать для заполнения импорта. В данном случае причина в том, что сама эта часть была отклонена из-за отсутствующих импортируемых элементов.  
  
<a name="analyzing_primary_causes"></a>   
## <a name="analyzing-primary-causes"></a>Анализ основных причин  
 Если несколько частей связаны в длинную цепочку зависимостей, проблема с частью в нижней области может стать причиной отклонения всей цепочки. Диагностировать эти проблемы может быть сложно, потому что причина сбоя не всегда очевидна. Чтобы упростить проблему, можно использовать действие `/causes` , которое пытается найти причину любого каскадного отклонения.  
  
 Если бы в предыдущем примере использовалось действие `/causes` , удалось бы вывести только информацию для части `ChainOne`, незаполненный импорт которой является основной причиной отклонения `AddIn`. Действие `/causes` можно использовать в обычном режиме и с параметрами `/verbose` .  
  
> [!NOTE]
> В большинстве случаев Mefx сможет диагностировать основную причину каскадного сбоя. Однако в тех случаях, когда части программным способом добавляются в контейнер, Mefx не сможет диагностировать причину проблемы, если задействованы иерархические контейнеры или пользовательские реализации `ExportProvider` . В общем случае вышеописанных случаев следует по возможности избегать, поскольку сбои, как правило, сложно диагностировать.  
  
<a name="white_lists"></a>   
## <a name="white-lists"></a>Белые списки  
 Параметр `/whitelist` позволяет задать текстовый файл с перечислением частей, которые, как ожидается, будут отклонены. Непредвиденные отклонения будут помечены. Это может быть полезным при анализе неполной библиотеки или вложенной библиотеки, в которой отсутствуют некоторые зависимости. Параметр `/whitelist` можно применить к действиям `/rejected` или `/causes` .  
  
 Рассмотрим файл с именем test.txt, который содержит текст ClassLibrary1.ChainOne. При запуске действия `/rejected` с параметром `/whitelist` в предыдущем примере будут получены следующие выходные данные.  
  
```console
mefx /file:ClassLibrary1.dll /rejected /whitelist:test.txt  
[Unexpected] ClassLibrary1.AddIn  
ClassLibrary1.ChainOne  
```
