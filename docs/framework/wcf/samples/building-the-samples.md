---
title: "Построение примеров Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d5de916aa5825625f29efe316571ad5085afb431
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="building-the-windows-communication-foundation-samples"></a>Построение примеров Windows Communication Foundation
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Образцы, которые могут быть построены с использованием Visual Studio 2010 или **msbuild** команду из командной строки. В этом разделе описаны обе эти процедуры.  
  
> [!NOTE]
>  До построения или выполнением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] образцы, убедитесь, что выполнена [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
### <a name="to-build-the-sample-using-a-command-prompt"></a>Сборка образца с использованием командной строки  
  
1.  Откройте командную строку [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с правами администратора и перейдите в подкаталог языка в каталоге установки образца.  
  
2.  Тип `msbuild` из командной строки. Файлы построения клиентской программы сохраняются в папке client\bin, а файлы построения служебной программы - в папке service\bin. Если служба размещена в службах IIS, то файлы служебной программы также копируются в каталог servicemodelsamples и его подкаталог \bin.  
  
> [!NOTE]
>  Необходимо задать списки управления доступом для каталога %systemdrive%\inetpub\wwwroot, чтобы предоставить разрешения на изменение учетной записи, от имени которой выполняются операции. В противном случае некоторые события построения могут завершиться сбоем. Либо можно оставить списки управления доступом неизменными и запускать командную строку пакета SDK от имени администратора.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Сборка образца с использованием Visual Studio  
  
1.  Если используется [!INCLUDE[wv](../../../../includes/wv-md.md)] или [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7, Windows Server 2008 R2 или [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], то необходимо запускать [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] с повышенными разрешениями. Чтобы сделать это, щелкните правой кнопкой мыши значок в меню «Пуск» и нажмите кнопку **Запуск от имени администратора**.  
  
2.  Из **файл** меню в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], нажмите кнопку **откройте**, нажмите кнопку **проект или решение**. Перейдите к языковому подкаталогу каталога, в котором установлен образец, и дважды щелкните значок файла SLN, чтобы открыть решение в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
3.  В **построения** последовательно выберите пункты **Перестроить решение**. Файлы построения клиентской программы сохраняются в папке client\bin, а файлы построения служебной программы - в папке service\bin. Если служба размещена в службах IIS, файлы служебной программы также копируются в каталог servicemodelsamples и его подкаталог \bin.  
  
> [!NOTE]
>  Необходимо задать списки управления доступом для каталога %systemdrive%\inetpub\wwwroot, чтобы предоставить разрешения на изменение учетной записи, от имени которой выполняются операции. В противном случае некоторые события построения могут завершиться сбоем. Либо можно оставить списки управления доступом неизменными и запускать командную строку SDK или Visual Studio от имени администратора. Некоторые операции Visual Studio (например, прикрепление отладчика к рабочему процессу ASP.Net) также требуют прав администратора.  
  
## <a name="setup-batch-files-and-scripts"></a>Пакетные файлы и скрипты установки  
 Пакетные файлы и скрипты Setup.exe и Cleanup.exe должны запускаться из командной строки Visual Studio. Некоторые файлы установки и очистки выполняют задачи, требующие прав администратора, и должны запускаться с этими правами.  
  
## <a name="important-security-information-about-metadata-endpoints"></a>Важные сведения по безопасности конечных точек метаданных  
 Чтобы предотвратить непреднамеренное разглашение потенциально важных метаданных службы, в конфигурации служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] публикация метаданных по умолчанию отключена. Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации. Чтобы испытывать образец было проще, почти все образцы предоставляют незащищенную конечную точку публикации метаданных. Такие конечные точки являются потенциально доступными для анонимных не прошедших проверку подлинности потребителей, поэтому перед развертыванием таких конечных точек следует соблюдать осторожность и убедиться, что публичное раскрытие метаданных службы уместно. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Публикация метаданных службы. в разделе [поведения публикации метаданных](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) образца. В разделе [конечной точки метаданных защиты пользовательских](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) примера образец защиты конечной точки метаданных.  
  
## <a name="exception-handling"></a>Обработка исключений  
 В целом эти образцы не включают обработку исключений для того, чтобы код был сконцентрирован на теме образца. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Обработка исключений, в разделе [ожидаемого исключения](../../../../docs/framework/wcf/samples/expected-exceptions.md) образца.  
  
## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Восстановление клиентов и конфигурации с помощью средства Svcutil  
 Можно использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для повторного создания кода клиента и конфигурации для большинства образцов. Некоторые образцах требуют редактирования конфигурации вручную. Например, если средство Svcutil.exe используется для восстановления конфигурации образца, использующего учетные данные сертификата клиента, необходимо вручную указать ранее заданные учетные данные. В некоторых образцах используются особые параметры средства Svcutil.exe, влияющие на создаваемый код; эти параметры описаны в соответствующих разделах образце.  
  
#### <a name="to-regenerate-the-client-and-configuration-files"></a>Восстановление клиента и файлов конфигурации  
  
1.  Откройте окно командной строки SDK и перейдите к языковому подкаталогу в каталоге, где установлен образец.  
  
2.  Если служба размещается на веб-сервере, воспользуйтесь следующей командой.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Если служба размещается резидентно, воспользуйтесь следующей командой.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Замените адрес http://localhost:8000/ServiceModelSamples/service.svc/mex на адрес конечной точки mex размещенной резидентно службы.  
  
     Чтобы создать клиент на языке Visual Basic, воспользуйтесь следующей командой.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
     Если служба размещается резидентно, воспользуйтесь следующей командой.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
    > [!NOTE]
    >  Чтобы пропустить создание конфигурации клиента добавьте **/noconfig** параметр.  
  
## <a name="see-also"></a>См. также  
 [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md)  
 [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
