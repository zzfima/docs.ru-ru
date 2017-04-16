---
title: "@ServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# @ServiceHost
Связывает фабрику, используемую для создания узла службы, с размещаемой службой и другими элементами программирования, необходимыми для доступа или компиляции кода размещения, представленного в SVC\-файле.  
  
## Синтаксис  
  
```  
  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## Атрибуты  
  
#### Служба  
 Имя типа CLR размещенной службы.  Это должно быть полное имя типа, который реализует один или несколько контактов службы.  
  
#### Factory  
 Имя типа CLR фабрики узла службы, используемой для создания узла службы.  Этот атрибут является необязательным.  Если данный атрибут не задан, по умолчанию используется значение <xref:System.ServiceModel.Activation.ServiceHostFactory>, которое возвращает экземпляр <xref:System.ServiceModel.ServiceHost>.  
  
#### Отладка  
 Указывает, должна ли служба [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] компилироваться с помощью символов отладки.  Если для компиляции службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] должны использоваться символы отладки, следует задать значение `true`, в противном случае \- значение `false`.  
  
#### Язык  
 Задает язык, используемый при компиляции всего встроенного кода в файле \(SVC\).  Значения данного атрибута могут представлять любой язык, поддерживаемый .NET, включая C\#, VB и JS, что соответствует языкам C\#, Visual Basic .NET и JScript .NET.  Этот атрибут является необязательным.  
  
#### CodeBehind  
 Определяет файл исходного кода, реализующего веб\-службу XML, если реализующий ее класс находится в другом файле и не был скомпилирован в сборку и помещен в каталог «\\Bin».  
  
## Заметки  
 <xref:System.ServiceModel.ServiceHost>, используемый для размещения службы, представляет точку расширения в программной модели [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  Для создания узла службы <xref:System.ServiceModel.ServiceHost> используется шаблон фабрики, поскольку он, возможно, имеет полиморфный тип, экземпляр которого среда размещения не должна создавать явно.  
  
 В реализации по умолчанию используется фабрика <xref:System.ServiceModel.Activation.ServiceHostFactory> для создания экземпляра узла службы <xref:System.ServiceModel.ServiceHost>.  Но можно предоставить собственную фабрику \(которая возвращает производный узел\), указав имя типа CLR реализации фабрики в директиве [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
 Для использования пользовательской фабрики узла службы необходимо указать имя типа в директиве [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) следующим образом:  
  
```  
<% @ServiceHost Factory=”DerivedFactory” Service=”MyService” %>  
```  
  
 Создавайте реализацию фабрики в наиболее простом виде.  Если имеется значительный объем пользовательской логики, то можно увеличить возможность повторного использования кода, если разместить эту логику на узле, а не в фабрике.  
  
 Например, чтобы включить конечную точку с поддержкой технологии AJAX для `MyService`, задайте <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> для значения атрибута `Factory` вместо значения по умолчанию <xref:System.ServiceModel.Activation.ServiceHostFactory> в директиве [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md), как показано в следующем примере.  
  
## Пример  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## См. также  
 [Пользовательский узел службы](../../../../../docs/framework/wcf/samples/custom-service-host.md)