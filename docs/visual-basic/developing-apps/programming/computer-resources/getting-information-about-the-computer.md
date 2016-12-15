---
title: "Получение сведений о компьютере (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.Info - объект, задачи"
ms.assetid: 13c145bc-5c85-4fea-a5dd-2ca8681a0252
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Получение сведений о компьютере (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект `My.Computer.Info` содержит свойства, которые можно использовать для получения сведений о памяти компьютера, загруженных сборках, имени и операционной системе.  
  
## Заметки  
 В этой таблице перечислены типичные задачи, выполняемые с помощью объекта `My.Computer.Info`, и указаны разделы, демонстрирующие их выполнение.  
  
|||  
|-|-|  
|Целевой тип|См.|  
|Определение объема виртуального адресного пространства, доступного на компьютере, на котором установлено приложение|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.TotalVirtualMemory%2A>|  
|Определение типа платформы компьютера, на котором выполняется приложение|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSPlatform%2A>|  
|Определение операционной системы компьютера, на котором выполняется приложение|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName%2A>|  
|Определение пакетов обновления, установленных на компьютере, на котором выполняется приложение|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSVersion%2A>|  
|Определение установленных интерфейсов `UICulture` на компьютере, на котором выполняется приложение.|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.InstalledUICulture%2A>|  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>