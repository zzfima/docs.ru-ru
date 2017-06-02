---
title: "Изменения среды выполнения в .NET Framework 4.5.2 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94ac01ea-8b12-44d2-b12b-5220a5d14d87
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Изменения среды выполнения в .NET Framework 4.5.2
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, предназначенные для предыдущих версий .NET Framework, но выполняющиеся в среде выполнения .NET Framework 4.5.2. Они включают изменения в следующих областях.  
  
-   [ASP.NET](#ASP_NET)  
  
-   [Entity Framework](#EF)  
  
<a name="ASP_NET"></a>   
## Изменения среды выполнения ASP.NET  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Атрибут `enableViewStateMac`[элемента страниц](http://msdn.microsoft.com/ru-ru/4123bb66-3fe4-4d62-b70e-33758656b458)|ASP.NET теперь не позволяет разработчикам указывать:<br /><br /> `<pages enableViewStateMac="false" />`<br /><br /> или<br /><br /> `<@Page EnableViewStateMac="false" %>`|Код проверки подлинности сообщения \(MAC\) состояния просмотра теперь принудительно применяется для всех запросов со встроенным состоянием просмотра. Затрагиваются только те приложения, в которых для свойства <xref:System.Web.UI.Page.EnableViewStateMac%2A> явно задано значение `false`.<br /><br /> Дополнительные сведения см. в статье [Устранение ошибок, связанных с состоянием вида кода проверки подлинности сообщения \(MAC\)](http://support.microsoft.com/kb/2915218).|Значительно|  
  
<a name="EF"></a>   
## Изменения среды выполнения Entity Framework  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Отношения через представление QueryView|Entity Framework больше не создает исключение <xref:System.StackOverflowException>, если приложение выполняет запрос, включающий представление QueryView со свойством навигации 0..1, которое пытается включить связанные объекты в запрос \(например, вызывая метод `.Include(e=>e.RelatedNavProp)`\).|Это изменение влияет только на код, использующий представления QueryView с отношениями 1\-0..1 при выполнении запросов, вызывающих метод `.Include`. Эта функция повышает надежность и должна быть прозрачна почти для всех приложений. Тем не менее, если она вызывает непредвиденное поведение, ее можно отключить, добавив следующую запись в раздел `<appSettings>` файла конфигурации приложения:<br /><br /> `<add key="EntityFramework_SimplifyUserSpecifiedViews"  value="false" />`|Пограничный случай|  
  
## См. также  
 [Изменения целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)   
 [Совместимость приложений в платформе 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Совместимость приложений в платформе 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)