---
title: Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
manager: douge
ms.openlocfilehash: 15ef15e0afe43d56db0972a686cd093e22c672dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)
В этом примере используется <xref:System.ServiceProcess.ServiceController> компонента, чтобы продолжить работу службы администрирования IIS на локальном компьютере.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он находится в **операционная система Windows > службы Windows**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылка проекта System.serviceprocess.dll.  
  
-   Доступ к членам пространства имен <xref:System.ServiceProcess>. Добавьте оператор `Imports`, если в коде не используются полные имена членов. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 <xref:System.ServiceProcess.ServiceController.MachineName%2A> Свойство <xref:System.ServiceProcess.ServiceController> класса — локальный компьютер по умолчанию. Чтобы обратиться к службам Windows на другом компьютере, измените <xref:System.ServiceProcess.ServiceController.MachineName%2A> на имя этого компьютера.  
  
 Не удается вызвать <xref:System.ServiceProcess.ServiceController.Continue%2A> метод службы, пока состояние контроллера службы — <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Служба не может быть возобновлен. (<xref:System.InvalidOperationException>)  
  
-   Произошла ошибка при обращении к API-интерфейсу системы. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Управление службами на компьютере может быть ограничен с помощью <xref:System.ServiceProcess.ServiceControllerPermissionAccess> перечисления для задания разрешений в <xref:System.ServiceProcess.ServiceControllerPermission> класса.  
  
 Доступ к сведениям служб может быть ограничен с помощью <xref:System.Security.Permissions.PermissionState> перечисления для задания разрешений в <xref:System.Security.Permissions.SecurityPermission> класса.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
