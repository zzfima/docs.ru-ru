---
title: "Уменьшение: управление версиями продукта | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Уменьшение: управление версиями продукта
В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и 4.6.1 управление версиями продукта отличается от предыдущих версий платформы .NET Framework \(.NET Framework 4, 4.5, 4.5.1 и 4.5.2\).  
  
## Изменения управления версиями продукта  
 Ниже приведено подробное описание изменений.  
  
-   Значение записи `Version` в ключе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` изменено на `4.6.`*xxxxx*. В .NET Framework 4.5, 4.5.1 и 4.5.2 использовался формат `4.5.`*xxxxx*.  
  
-   Управление версиями файлов и продукта для .NET Framework было изменено на `4.6.X.0` с более ранней схемы управления версиями `4.0.30319.x`. Вы можете увидеть эти новые значения в **свойствах** файла, щелкнув его  правой кнопкой мыши.  
  
-   Атрибуты <xref:System.Reflection.AssemblyFileVersionAttribute> и <xref:System.Reflection.AssemblyInformationalVersionAttribute> управляемых сборок имеют значения <xref:System.Version> в форме `4.6.X.0`  
  
-   В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и 4.6.1 свойство <xref:System.Environment.Version%2A?displayProperty=fullName> возвращает исправленную строку версии `4.0.30319.42000`. В .NET Framework 4, 4.5, 4.5.1 и 4.5.2 оно возвращает строки версии в формате `4.0.30319.xxxxx` \(например, «4.0.30319.18010»\). Обратите внимание, что создание в свойстве <xref:System.Environment.Version%2A?displayProperty=fullName> новых зависимостей от кода приложения не рекомендуется.  
  
### Обработка изменений управления версиями продукта  
 В общем случае приложения для обнаружения таких сведений, как версия среды выполнения .NET Framework и каталог установки, должны использовать следующие рекомендуемые методы:  
  
-   Чтобы определить версию среды выполнения .NET Framework, см. раздел [Практическое руководство.Определение установленных версий платформы .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).  
  
-   Чтобы определить путь установки платформы .NET Framework, используйте значение записи `InstallPath` в ключе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`.  
  
    > [!IMPORTANT]
    >  Имя подраздела — `NET Framework Setup`, а не `.NET Framework Setup`.  
  
-   Чтобы определить путь к каталогу общеязыковой среды выполнения .NET Framework, вызовите метод <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=fullName>.  
  
-   Чтобы получить версию среды CLR, вызовите метод <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=fullName>.   Для .NET Framework 4 и ее доработанных выпусков \(.NET Framework 4.5, 4.5.1, 4.5.2, [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и 4.6.1\) возвращается строка `v4.0.30319`.  
  
## См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)