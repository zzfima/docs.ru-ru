---
title: Сохраняемая задержка
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 5307b8144e17f91cd3ba8c2e385492f86c167820
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="durable-delay"></a>Сохраняемая задержка
В этом образце показано, как использовать сохраняемую задержку, при которой рабочий процесс сохраняется на физическом устройстве. Образец рабочего процесса содержит два сообщения на консоль, разделенных задержкой. Когда запускается задержка, рабочий процесс выгружается и в течение 5 секунд хранится в хранилище экземпляров рабочих процессов, а затем снова загружается в память.  
  
## <a name="workflow-details"></a>Подробные сведения о рабочем процессе  
 Узел службы рабочего процесса, на котором размещен рабочий процесс, управляет экземплярами рабочих процессов, загружая и выгружая их. Для запуска экземпляра определения рабочего процесса в образце создается прокси, отправляющий сообщение действию <xref:System.ServiceModel.Activities.Receive> в рабочем процессе. Свойство <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> устанавливается в значение `true`, что позволяет ему после получения сообщения создать новый экземпляр рабочего процесса.  
  
 В следующем списке показана настройка узла службы рабочего процесса во время инициализации.  
  
1.  Создает узел службы с адресом (http://localhost:8080/Client).  
  
2.  Создается конечная точка в узле службы для обеспечения взаимодействия с действием <xref:System.ServiceModel.Activities.Receive> в рабочем процессе.  
  
3.  Настраивается хранилище экземпляров SQL.  
  
4.  Добавляется поведение выгрузки экземпляра, устанавливающее условия, при которых узел службы рабочего процесса будет производить выгрузку экземпляров рабочего процесса в хранилище сохраняемости SQL. В этом образце экземпляр выгружается сразу после того, как рабочий процесс становится бездействующим (когда запускается задержка).  
  
5.  Создается прокси, отправляющий сообщение действию <xref:System.ServiceModel.Activities.Receive> в рабочем процессе.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Настройка базы данных сохраняемости.  
  
    1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Перейдите к [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] каталога (C:\Windows\Microsoft.NET\Framework\v4. X\\).  
  
    3.  Измените файл WorkflowManagementService.exe.config и добавьте следующую строку подключения в элемент <`database`>.  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  Перейдите в каталог DurableDelay\CS.  
  
    5.  Запустите команду Setup.cmd.  
  
2.  Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными правами, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.  
  
3.  Откройте файл решения Delay.sln.  
  
4.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
5.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
#### <a name="to-uninstall-this-sample"></a>Удаление этого образца  
  
1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Перейдите в каталог DurableDelay\CS.  
  
3.  Запустите команду Cleanup.cmd.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`