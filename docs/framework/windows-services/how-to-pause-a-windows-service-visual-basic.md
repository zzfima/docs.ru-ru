---
title: "How to: Pause a Windows Service (Visual Basic) | Microsoft Docs"
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
  - "ServiceController.Pause"
helpviewer_keywords: 
  - "Windows Service applications, pausing"
  - "pausing Windows Service applications"
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 15
---
# How to: Pause a Windows Service (Visual Basic)
В этом примере компонент <xref:System.ServiceProcess.ServiceController> используется для приостановки службы IIS Admin на локальном компьютере.  
  
## Пример  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows \> Службы Windows**.  Дополнительные сведения см. в разделе [Фрагменты кода](../Topic/Code%20Snippets.md).  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка на System.serviceprocess.dll;  
  
-   Доступ к элементам пространства имен <xref:System.ServiceProcess>.  Добавьте оператор `Imports`, если в коде не используются полностью квалифицированные имена элементов.  Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен .NET и тип\)](../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Отказоустойчивость  
 Свойство <xref:System.ServiceProcess.ServiceController.MachineName%2A> класса <xref:System.ServiceProcess.ServiceController> по умолчанию соответствует локальному компьютеру.  Чтобы обратиться к службам Windows на другом компьютере, следует изменить значение свойства <xref:System.ServiceProcess.ServiceController.MachineName%2A> на имя этого компьютера.  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Приостановка службы невозможна  \([класс InvalidOperationException](frlrfSystemInvalidOperationExceptionClassTopic)\);  
  
-   Произошла ошибка при обращении к системному API   \([класс Win32Exception](frlrfSystemComponentModelWin32ExceptionClassTopic)\).  
  
## Безопасность платформы .NET Framework  
 Управление службами на компьютере может быть ограничено с помощью [перечисления ServiceControllerPermissionAccess](frlrfSystemServiceProcessServiceControllerPermissionAccessClassTopic), используемого для задания разрешений в [классе ServiceControllerPermission](frlrfSystemServiceProcessServiceControllerPermissionClassTopic).  
  
 Доступ к сведениям о службе может быть ограничен с помощью [перечисления PermissionState](frlrfSystemSecurityPermissionsPermissionStateClassTopic), используемого для задания разрешений в [классе SecurityPermission](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic).  
  
## См. также  
 <xref:System.ServiceProcess.ServiceController>   
 <xref:System.ServiceProcess.ServiceControllerStatus>   
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>   
 [How to: Continue a Windows Service \(Visual Basic\)](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)