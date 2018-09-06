---
title: Построение примеров Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 46f4015c00916a5cab932e8fd2539c7c86588a30
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43774038"
---
# <a name="building-the-windows-communication-foundation-samples"></a>Построение примеров Windows Communication Foundation

Примеры Windows Communication Foundation (WCF) может быть построен в интегрированной среде разработки Visual Studio или с помощью **msbuild** команду из командной строки. В этом разделе описаны обе эти процедуры.

> [!NOTE]
> Перед построением или выполнением любого из образцов WCF, убедитесь, что выполнена [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

## <a name="to-build-the-sample-using-a-command-prompt"></a>Сборка образца с использованием командной строки

1.  Откройте командную строку разработчика для Visual Studio и перейдите к языковому подкаталогу в каталоге, где установлен пример.

2.  Тип `msbuild` в командной строке. Файлы программы клиента предназначены для *client\bin* и встроенных файлы служебной программы *service\bin*. Если служба размещается в Internet Information Services (IIS), файлы служебной программы также копируются *servicemodelsamples* каталог и его *\bin* подкаталог.

> [!NOTE]
> Необходимо задать списки управления доступом на *%systemdrive%\inetpub\wwwroot* предоставление измененных разрешений для учетной записи, под которой выполняется. В противном случае некоторые события построения могут завершиться сбоем. Либо можно оставить списки управления доступом неизменными и запускать командную строку пакета SDK от имени администратора.

## <a name="to-build-the-sample-using-visual-studio"></a>Сборка образца с использованием Visual Studio

1. Из **файл** меню в Visual Studio, выберите пункт **откройте** > **решение или проект**. Перейдите к языковому подкаталогу в каталоге, в котором установлен образец и дважды щелкните значок файла SLN, чтобы открыть решение в Visual Studio.

1. Из **построения** меню, выберите **Перестроить решение**.

   Файлы построения клиентской программы сохраняются в папке client\bin, а файлы построения служебной программы - в папке service\bin. Если служба размещается в службах IIS, файлы служебной программы также копируются *servicemodelsamples* каталог и его *\bin* подкаталог.

> [!NOTE]
> Необходимо задать списки управления доступом для каталога %systemdrive%\inetpub\wwwroot, чтобы предоставить разрешения на изменение учетной записи, от имени которой выполняются операции. В противном случае некоторые события построения могут завершиться сбоем. Либо можно оставить списки управления доступом неизменными и запускать командную строку SDK или Visual Studio от имени администратора. Некоторые операции Visual Studio (например, прикрепление отладчика к рабочему процессу ASP.Net) также требуют прав администратора.

## <a name="setup-batch-files-and-scripts"></a>Пакетные файлы и скрипты установки
 Setup.exe и Cleanup.exe пакетные файлы и скрипты должны запускаться из командной строки разработчика для Visual Studio. Некоторые файлы установки и очистки выполняют задачи, требующие прав администратора, и должны запускаться с этими правами.

## <a name="important-security-information-about-metadata-endpoints"></a>Важные сведения по безопасности конечных точек метаданных
 Чтобы предотвратить непреднамеренное разглашение потенциально важных метаданных службы, конфигурация по умолчанию для служб Windows Communication Foundation (WCF) отключает публикацию метаданных. Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации. Чтобы испытывать образец было проще, почти все образцы предоставляют незащищенную конечную точку публикации метаданных. Такие конечные точки являются потенциально доступными для анонимных не прошедших проверку подлинности потребителей, поэтому перед развертыванием таких конечных точек следует соблюдать осторожность и убедиться, что публичное раскрытие метаданных службы уместно. Дополнительные сведения о публикации метаданных службы, см. в разделе [поведения публикации метаданных](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) образца. См. в разделе [конечной точки метаданных Secure Custom](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) образец для образца, который защищает конечную точку метаданных.

## <a name="exception-handling"></a>Обработка исключений
 В целом эти образцы не включают обработку исключений для того, чтобы код был сконцентрирован на теме образца. Дополнительные сведения об обработке исключений см. в разделе [ожидается исключения](../../../../docs/framework/wcf/samples/expected-exceptions.md) образца.

## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Восстановление клиентов и конфигурации с помощью средства Svcutil
 Можно использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для повторного создания кода клиента и конфигурации для большинства образцов. Некоторые образцах требуют редактирования конфигурации вручную. Например, если средство Svcutil.exe используется для восстановления конфигурации образца, использующего учетные данные сертификата клиента, необходимо вручную указать ранее заданные учетные данные. В некоторых образцах используются особые параметры средства Svcutil.exe, влияющие на создаваемый код; эти параметры описаны в соответствующих разделах образце.

### <a name="to-regenerate-the-client-and-configuration-files"></a>Восстановление клиента и файлов конфигурации

1.  Откройте окно командной строки SDK и перейдите к языковому подкаталогу в каталоге, где установлен образец.

2.  Если служба размещается на веб-сервере, воспользуйтесь следующей командой.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Если служба размещается резидентно, воспользуйтесь следующей командой.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Замените http://localhost:8000/ServiceModelSamples/service.svc/mex с адресом конечной точки mex резидентной службы.

     Чтобы создать клиент на языке Visual Basic, воспользуйтесь следующей командой.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     Если служба размещается резидентно, воспользуйтесь следующей командой.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > Чтобы пропустить создание конфигурации клиента, добавьте **/noconfig** параметр.

## <a name="see-also"></a>См. также

- [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md)
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
