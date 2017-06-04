---
title: "Указание расположения сборки | Microsoft Docs"
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
  - "конфигурация приложений [платформа .NET Framework]"
  - "сборки [платформа .NET Framework], указание места"
  - "конфигурация [платформа .NET Framework], приложения"
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Указание расположения сборки
Существует два способа задания расположения сборок.  
  
-   Использование элемента [\<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md).  
  
-   Использование элемента [\<probing\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md).  
  
 Можно также использовать [инструмент настройки платформы платформы .NET Framework \(Mscorcfg.msc\)](http://msdn.microsoft.com/ru-ru/a7106c52-68da-490e-b129-971b2c743764), чтобы задавать расположение сборки или расположения для поиска средой CLR.  
  
## Использование элемента \<codeBase\>  
 Элемент **\<codeBase\>** можно использовать только в файле конфигурации компьютера или файле политики издателя, которые также предоставляют перенаправление версии сборки.  Когда среда выполнения определит, какая из версий сборок будет использоваться, она применяет параметр базы кода из файла, определяющего версию.  Если база кода не указана, среда выполняет поиск сборки обычным образом.  Дополнительные сведения содержатся в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 В следующем примере показан способ задания расположения сборки.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Атрибут **version** требуется для всех сборок со строгим именем, но должен быть опущен для сборок, не имеющих строгих имен.  Элементу **\<codeBase\>** требуется атрибут **href**.  В элементе **\<codeBase\>** нельзя определить диапазон версий.  
  
> [!NOTE]
>  Подсказка базы кода, если она предоставлена для сборки без строгого имени, должна указывать на базу приложения или на подкаталог каталога базы приложения.  
  
## Использование элемента \<probing\>  
 Среда выполнения определяет расположение сборок, не имеющих базы кода, путем поиска.  Дополнительные сведения о поиске содержатся в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Для указания подкаталогов, которые среда выполнения должна использовать при определении расположения сборки, может быть использован элемент [\<probing\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) в файле конфигурации приложения.  В следующем примере показан способ задания каталогов, в которых среда выполнения должна производить поиск.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Атрибут **privatePath** содержит те каталоги, в которых среда выполнения должна осуществлять поиск сборок.  Если приложение находится в C:\\Program Files\\MyApp, среда выполнения будет искать сборки, в которых не указана база кода, по адресам C:\\Program Files\\MyApp\\Bin, C:\\Program Files\\MyApp\\Bin2\\Subbin и C:\\Program Files\\MyApp\\Bin3.  Каталоги, заданные в **privatePath**, должны являться подкаталогами для каталога базы приложения.  
  
## См. также  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/ru-ru/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)