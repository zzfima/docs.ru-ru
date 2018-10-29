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
ms.openlocfilehash: 255dccfb74eced63ffbeff7ef567083a504cc6da
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48027290"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)
В этом примере для возобновления работы службы администрирования IIS на локальном компьютере используется компонент <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows > Службы Windows**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылка в проекте на System.serviceprocess.dll.  
  
-   Доступ к членам пространства имен <xref:System.ServiceProcess>. Добавьте оператор `Imports`, если в коде не используются полные имена членов. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Свойство <xref:System.ServiceProcess.ServiceController.MachineName%2A> класса <xref:System.ServiceProcess.ServiceController> — это по умолчанию локальный компьютер. Чтобы указать ссылку на службы Windows на другом компьютере, укажите в свойстве <xref:System.ServiceProcess.ServiceController.MachineName%2A> имя другого компьютера.  
  
 Пока контроллер службы находится в состоянии <xref:System.ServiceProcess.ServiceControllerStatus.Paused>, вызывать для службы метод <xref:System.ServiceProcess.ServiceController.Continue%2A> нельзя.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Не удалось возобновить работу службы. (<xref:System.InvalidOperationException>)  
  
-   Произошла ошибка при обращении к API-интерфейсу системы. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы ограничить управление службами на компьютере, с помощью перечисления <xref:System.ServiceProcess.ServiceControllerPermissionAccess> настройте в классе <xref:System.ServiceProcess.ServiceControllerPermission> необходимые разрешения.  
  
 Чтобы ограничить доступ к сведениям о службе, с помощью перечисления <xref:System.Security.Permissions.PermissionState> настройте в классе <xref:System.Security.Permissions.SecurityPermission> необходимые разрешения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
