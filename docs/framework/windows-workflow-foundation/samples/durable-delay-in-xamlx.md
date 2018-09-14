---
title: Сохраняемая задержка в XAMLX
ms.date: 03/30/2017
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
ms.openlocfilehash: 1eef9211c67d190ecb5f329c481fa2e3d1763353
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45594112"
---
# <a name="durable-delay-in-xamlx"></a>Сохраняемая задержка в XAMLX
В этом образце показано, как использовать сохраняемую задержку, при которой рабочий процесс сохраняется на физическом устройстве.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>Обсуждение  
 Образец рабочего процесса содержит два сообщения для локального файла, разделенных задержкой. Когда запускается задержка, рабочий процесс выгружается и в течение 5 секунд хранится в хранилище экземпляров рабочих процессов, а затем снова загружается в память.  
  
 Xamlx-файл — это служба рабочего процесса, который размещен в Visual Studio. Visual Studio использует сервер Cassini, использующий службы рабочего процесса узла на другой рабочий процесс.  
  
 Кроме размещения рабочего процесса, узел службы рабочего процесса управляет экземплярами рабочих процессов, загружая их и выгружая. Для запуска экземпляра определения Windows Workflow Foundation (WF) (на узле службы рабочего процесса), укажите клиент, который отправляет сообщение <xref:System.ServiceModel.Activities.Receive> действия в рабочем процессе. Объект <xref:System.ServiceModel.Activities.Receive> используется со значением свойства <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>, равным `true`, что позволяет ему создать новый экземпляр рабочего процесса при получении сообщения.  
  
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
