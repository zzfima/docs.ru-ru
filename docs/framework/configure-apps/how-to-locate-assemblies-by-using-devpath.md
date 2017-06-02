---
title: "Практическое руководство. Поиск сборок с помощью DEVPATH | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "конфигурация приложений .NET Framework, сборки"
  - "файлы app.config, расположения сборок"
  - "файлы конфигурации приложений, указание расположения сборки"
  - "сборки [платформа .NET Framework], расположение"
  - "DEVPATH"
  - "расположение сборок"
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Практическое руководство. Поиск сборок с помощью DEVPATH
У разработчиков может возникнуть желание убедиться, что создаваемая общая сборка работает корректно с несколькими приложениями.  На этапе разработки, вместо того чтобы постоянно помещать сборку в глобальный кэш сборок, разработчик может создать переменную среды DEVPATH, которая указывает на выходной каталог построения для сборки.  
  
 Предположим, что строится общая сборка с именем MySharedAssembly и имеется выходной каталог C:\\MySharedAssembly\\Debug.  Можно внести C:\\MySharedAssembly\\Debug в переменную DEVPATH.  Для этого нужно задать элемент [\<developmentMode\>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) в файле конфигурации компьютера.  Этот элемент предписывает среде CLR использовать DEVPATH для обнаружения сборок.  
  
 Общая сборка должна поддаваться обнаружению средой выполнения.  Чтобы указать закрытый каталог для обработки ссылок на сборки, используйте [Элемент \<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) или [Элемент \<probing\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) в файле конфигурации в соответствии с разделом [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).  Также можно поместить сборку в подкаталог каталога приложения.  Для получения дополнительной информации см. [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Это дополнительная функция, предназначенная для использования только в процессе разработки.  
  
 В следующем примере показан способ выполнения средой выполнения поиска сборок в каталогах, указанных в переменной среды DEVPATH.  
  
## Пример  
  
```  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 Этот параметр используется по умолчанию со значением "false".  
  
> [!NOTE]
>  Этот параметр применяется только во время разработки.  Среда выполнения не проверяет версии указанных в DEVPATH сборок со строгими именами.  Она просто использует первую найденную сборку.  
  
## См. также  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/ru-ru/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)