---
title: Образец конечной точки управления рабочим процессом
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: e34a23f76edbd957b1be7caff1b18f6934b1588b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517102"
---
# <a name="workflow-management-endpoint-sample"></a>Образец конечной точки управления рабочим процессом
Этот образец показывает, как можно использовать конечную точку управления рабочего процесса для создания и запуска рабочих процессов как локально, так и удаленно. В следующем образце показано создание узла конечной точки управления, и клиентов, вызывающих конечную точку управления для создания и запуска экземпляра рабочего процесса. Рабочий процесс не является службой.  
  
 На стороне службы образца рабочий процесс размещен с помощью WorkflowServiceHost, а также добавлен WorkflowControlEndpoint, что позволяет клиентам выполнять операции управления (приостановка, запуск и т. д.). Добавлено также определяемое пользователем создание конечной точки CreationEndpoint, что позволяет создать рабочий процесс. Затем служба использует эти конечные точки для запуска рабочего процесса в приостановленном состоянии, а после этого возобновляет рабочий процесс. Клиент выполняет те же операции, но в коде клиента. Для Дополнительные сведения об этих интерфейсов см. в разделе [конечной точки управления рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) и [как: разместить не являющийся службой рабочий процесс в службах IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Запустите среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с правами администратора.  
  
2.  Откройте решение ManagementEndpoint.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.  
  
4.  Запустите приложение ManagementEndpoint.exe.  
  
5.  Запустите приложение Client.exe.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`