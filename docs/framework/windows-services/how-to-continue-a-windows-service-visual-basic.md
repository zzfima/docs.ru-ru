---
title: "How to: Continue a Windows Service (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceController.Continue"
helpviewer_keywords: 
  - "Windows Service applications, pausing"
  - "pausing Windows Service applications"
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 16
---
# How to: Continue a Windows Service (Visual Basic)
В этом руководстве компонент <xref:System.ServiceProcess.ServiceController> используется для возобновления работы службы IIS Admin на локальном компьютере.  
  
## Пример  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows \> Службы Windows**.  Дополнительные сведения см. в разделе [Фрагменты кода](../Topic/Code%20Snippets.md).  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка на System.serviceprocess.dll;  
  
-   Доступ к элементам пространства имен <xref:System.ServiceProcess>.  Добавьте оператор `Imports`, если в коде не используются полностью квалифицированные имена элементов.  Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен .NET и тип\)](../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Отказоустойчивость  
 Свойство <xref:System.ServiceProcess.ServiceController.MachineName%2A> класса <xref:System.ServiceProcess.ServiceController> по умолчанию соответствует локальному компьютеру.  Чтобы обратиться к службам Windows на другом компьютере, следует изменить значение свойства <xref:System.ServiceProcess.ServiceController.MachineName%2A> на имя этого компьютера.  
  
 Метод <xref:System.ServiceProcess.ServiceController.Continue%2A> нельзя вызывать до тех пор, пока контроллер службы не перейдет в состояние <xref:System.ServiceProcess.ServiceControllerStatus>.  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Возобновление службы невозможно  \(<xref:System.InvalidOperationException>\)  
  
-   Произошла ошибка при обращении к системному API   \(<xref:System.ComponentModel.Win32Exception>\)  
  
## Безопасность платформы .NET Framework  
 Управление службами на компьютере может быть ограничено с помощью перечисления <xref:System.ServiceProcess.ServiceControllerPermissionAccess> используемого для задания разрешений в классе <xref:System.ServiceProcess.ServiceControllerPermission>.  
  
 Доступ к сведениям служб может быть ограничен с помощью перечисления <xref:System.Security.Permissions.PermissionState>, используемого для задания разрешений в классе <xref:System.Security.Permissions.SecurityPermission>.  
  
## См. также  
 <xref:System.ServiceProcess.ServiceController>   
 <xref:System.ServiceProcess.ServiceControllerStatus>   
 [How to: Pause a Windows Service \(Visual Basic\)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)