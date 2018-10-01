---
title: Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: c62de97439ecf90ebfcc14d9fea4c5ab52f6ef73
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47230830"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a>Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)
В этом примере для приостановки работы службы администрирования IIS на локальном компьютере используется компонент <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows > Службы Windows**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылка в проекте на System.serviceprocess.dll.  
  
-   Доступ к членам пространства имен <xref:System.ServiceProcess>. Добавьте оператор `Imports`, если в коде не используются полные имена членов. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Свойство <xref:System.ServiceProcess.ServiceController.MachineName%2A> класса <xref:System.ServiceProcess.ServiceController> — это по умолчанию локальный компьютер. Чтобы указать ссылку на службы Windows на другом компьютере, укажите в свойстве <xref:System.ServiceProcess.ServiceController.MachineName%2A> имя другого компьютера.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Не удалось приостановить работу службы. (<xref:System.InvalidOperationException>)  
  
-   Произошла ошибка при обращении к API-интерфейсу системы. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы ограничить управление службами на компьютере, с помощью <xref:System.ServiceProcess.ServiceControllerPermissionAccess> настройте в <xref:System.ServiceProcess.ServiceControllerPermission> необходимые разрешения.  
  
 Чтобы ограничить доступ к сведениям о службе, с помощью <xref:System.Security.Permissions.PermissionState> настройте в <xref:System.Security.Permissions.SecurityPermission> необходимые разрешения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>  
 [Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)
