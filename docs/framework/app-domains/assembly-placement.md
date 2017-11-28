---
title: "Размещение сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c92ff8102cefbe6dcf89cfd8ddc636f0fc638b8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-placement"></a>Размещение сборок
Для большинства приложений .NET Framework сборки, составляющие приложение, располагаются в папке приложения, во вложенной папке этой папки или в глобальном кэше сборок (если сборка является совместно используемой). С помощью [элемента \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) в файле конфигурации можно изменить место, где среда CLR будет искать сборки. Если у сборки нет строгого имени, то расположение, которое указывается с помощью [элемента \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md), ограничивается папкой приложения или вложенной папкой этой папки. Если у сборки есть строгое имя, то [элемент \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) может указывать любое расположение на компьютере или в сети.  
  
 Аналогичные правила применяются к расположению сборок при работе с неуправляемым кодом или с приложениями, реализующими COM-взаимодействие: если сборка совместно используется несколькими приложениями, то она должна устанавливаться в глобальный кэш сборок. При использовании сборок с неуправляемым кодом их необходимо экспортировать в виде библиотеки типов и зарегистрировать. Сборки, использующиеся для обеспечения COM-взаимодействия, должны регистрироваться в каталоге, хотя в некоторых случаях такая регистрация производится автоматически.  
  
## <a name="see-also"></a>См. также  
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Настройка приложений](../../../docs/framework/configure-apps/index.md)  
 [Расширенное COM-взаимодействие](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
