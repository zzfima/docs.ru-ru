---
title: "Обзор графических возможностей | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "графика, о графике"
  - "графика, использование управляемых интерфейсов"
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Обзор графических возможностей
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] представляет собой интерфейс программирования \(API\), который формирует подсистему операционной системы Microsoft Windows. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] отвечает за отображение информации на экранах и принтерах.  Как видно из имени, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] является последователем [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], интерфейса графических устройств, входившего в состав более ранних версий Windows.  
  
## Интерфейс управляемых классов  
 API [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляется через набор классов, развертываемых в виде управляемого кода.  Этот набор классов называется *интерфейсом управляемых классов* для [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Интерфейс управляемых классов состоит из следующих пространств имен.  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 С помощью интерфейса графических устройств, такого как [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно отображать данные на экран или на принтер без необходимости думать о деталях для каждого конкретного устройства отображения.  Программист вызывает методы, предоставляемые классами [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Эти методы, в свою очередь, осуществляют вызовы драйверов определенных устройств.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] изолирует приложение от графического оборудования. Именно такая изоляция дает программистам возможность создавать приложения, не зависящие от устройства.  
  
## См. также  
 [Общие сведения о графике](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)