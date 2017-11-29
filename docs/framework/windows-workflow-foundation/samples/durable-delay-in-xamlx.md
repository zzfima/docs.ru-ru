---
title: "Сохраняемая задержка в XAMLX"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a52f3444b51f91d7076d6bc5a580d6efb6e26eb2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="durable-delay-in-xamlx"></a>Сохраняемая задержка в XAMLX
В этом образце показано, как использовать сохраняемую задержку, при которой рабочий процесс сохраняется на физическом устройстве.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>Обсуждение  
 Образец рабочего процесса содержит два сообщения для локального файла, разделенных задержкой. Когда запускается задержка, рабочий процесс выгружается и в течение 5 секунд хранится в хранилище экземпляров рабочих процессов, а затем снова загружается в память.  
  
 Файл XAMLX представляет собой службу Workflow Service, размещенную в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] использует сервер Cassini, в котором для размещения рабочего процесса применяется узел службы Workflow Service.  
  
 Кроме размещения рабочего процесса, узел службы рабочего процесса управляет экземплярами рабочих процессов, загружая их и выгружая. Для запуска экземпляра определения [!INCLUDE[wf](../../../../includes/wf-md.md)] (на узле службы рабочего процесса) укажите клиент, который отправляет сообщение действию <xref:System.ServiceModel.Activities.Receive> рабочего процесса. Объект <xref:System.ServiceModel.Activities.Receive> используется со значением свойства <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>, равным `true`, что позволяет ему создать новый экземпляр рабочего процесса при получении сообщения.  
  
 В процессе инициализации в файл конфигурации добавляется поведение выгрузки экземпляра, которое указывает узлу службы рабочего процесса, при каких обстоятельствах он должен выгружать экземпляр в хранилище (базу данных) сохраняемости. В этом образце экземпляр выгружается сразу после того, как рабочий процесс становится бездействующим (когда запускается задержка).  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Перейдите в папку DurableDelayXamlx\CS.  
  
3.  Запустите команду Setup.cmd.  
  
4.  Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] от имени администратора.  
  
5.  Откройте файл решения DurableDelayXamlx.sln.  
  
6.  В **обозревателе решений**, щелкните правой кнопкой мыши решение и выберите **свойства**.  
  
7.  Выберите **несколько запускаемых проектов** и задайте обоим проектам значение **запустить**.  
  
8.  Для построения решения нажмите CTRL+SHIFT+B.  
  
9. Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
#### <a name="to-uninstall-this-sample"></a>Удаление этого образца  
  
1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Перейдите в папку DurableDelayXamlx\CS.  
  
3.  Запустите команду Cleanup.cmd.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
