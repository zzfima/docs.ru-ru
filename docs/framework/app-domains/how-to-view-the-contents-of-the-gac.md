---
title: "Практическое руководство. Просмотр содержимого глобального кэша сборок | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "сборки [платформа .NET Framework], глобальный кэш сборок"
  - "GAC - глобальный кэш сборок, просмотр содержимого"
  - "Gacutil.exe"
  - "программа глобального кэша сборок"
  - "глобальный кэш сборок, просмотр содержимого"
  - "список сборок в глобальном кэше сборок"
  - "сборки со строгими именами, глобальный кэш сборок"
  - "просмотр сборок в глобальном кэше сборок"
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Просмотр содержимого глобального кэша сборок
Используйте [средство глобального кэша сборок \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) для просмотра содержимого глобального кэша сборок.  
  
### Просмотр списка сборок в глобальном кэше сборок  
  
1.  В [командной строке Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:  
  
     **gacutil \-l**   
     \-или\-               
     **gacutil \/l**  
  
 В предыдущих версиях .NET Framework с помощью расширения оболочки Windows [Shfusion.dll](http://msdn.microsoft.com/ru-ru/0d9464cf-ddba-4ca9-bbec-f678fb58f380) можно было просматривать глобальный кэш сборок в проводнике.  Начиная с версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], расширение оболочки Shfusion.dll является устаревшим.  
  
## См. также  
 [Работа со сборками и глобальным кэшем сборок](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)