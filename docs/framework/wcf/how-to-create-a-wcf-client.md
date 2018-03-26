---
title: Практическое руководство. Создание клиента Windows Communication Foundation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2591cad6354ec40f1fb6ead265c84a67adf3eec8
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Практическое руководство. Создание клиента Windows Communication Foundation
Это четвертый из шести шагов, необходимый для создания простого приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.  
  
 В данном разделе описывается, как извлечь метаданные из службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] и использовать, чтобы создать прокси [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для доступа к службе. Эта задача выполняется с помощью функции добавления ссылки на службу, предоставляемой средой Visual Studio. Данное средство получает метаданные из конечной точки обмена метаданными службы и создает файл управляемого исходного кода для клиентского прокси на выбранном языке (по умолчанию на C#). Кроме создания прокси клиента данное средство также создает или обновляет файл конфигурации клиента, позволяющий клиентскому приложению подключаться к службе в одной из конечных точек.  
  
> [!NOTE]
>  Можно также использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средства для создания класса прокси-сервера и конфигурации, вместо добавления ссылки на службу в Visual Studio.  
  
> [!WARNING]
>  При вызове службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] из проекта библиотеки учетной записи-посредника в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] можно использовать команду «Добавить ссылку на службу» для автоматического создания прокси и связанного файла конфигурации.  Файл конфигурации не будет использоваться проектом библиотеки классов. Необходимо добавить параметры из созданного файла конфигурации в файл app.config, соответствующий исполняемому файлу, вызывающему библиотеку классов.  
  
 Клиентское приложение использует созданный прокси-класс для взаимодействия со службой. Эта процедура описана в [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
### <a name="to-create-a-windows-communication-foundation-client"></a>Создание клиента Windows Communication Foundation  
  
1.  Создайте новый проект консольного приложения, щелкнув решение Приступая к работе, выбрав, **добавить**, **новый проект**. В **Добавление нового проекта** диалогового окна в левой части окна выберите **Windows** под **C#** или **VB**. В центральной части диалогового окна выберите **консольное приложение**. Задайте для проекта имя `GettingStartedClient`.  
  
2.  Значение целевой платформы проекта gettingstartedclient версию .NET Framework 4.5, щелкнув правой кнопкой мыши **GettingStartedClient** в обозревателе решений и выбрав **свойства**. В раскрывающемся списке **требуемой версии .NET Framework** выберите **.NET Framework 4.5**. Установка требуемой версии .NET framework для проекта Visual Basic несколько отличается, в диалоговом окне свойств проекта GettingStartedClient, нажмите кнопку **компиляции** с левой стороны экрана, а затем щелкните **Дополнительно Параметры компиляции** кнопки в левом нижнем углу диалогового окна. Выберите **.NET Framework 4.5** в раскрывающемся списке **требуемой версии .NET Framework**.  
  
     Требуемая версия .NET framework, то Visual Studio 2011 к перезагрузке решения, нажмите клавишу **ОК** при появлении запроса.  
  
3.  Добавление в проект GettingStartedClient ссылку на сборку System.ServiceModel щелкните правой кнопкой мыши **ссылки** папки проекта в обозревателе решений и выберите GettingStartedClient **добавить** Ссылка. В **добавить ссылку** окна выберите **Framework** с левой стороны диалогового окна. В текстовом поле «Поиск сборок» введите `System.ServiceModel`. В центральной части диалогового окна выберите **System.ServiceModel**, нажмите кнопку **добавить** и нажмите кнопку **закрыть** кнопки. Сохраните решение, нажав кнопку **сохранить все** кнопку под главным меню.  
  
4.  Затем необходимо добавить ссылку на службу калькулятора. Прежде чем это можно будет сделать, следует запустить консольное приложение GettingStartedHost. После запуска основного приложения можно правой кнопкой мыши папку References проекта GettingStartedClient в обозревателе решений и выберите Добавить ссылку на службу и введите следующий URL-адрес в поле "адрес" диалогового окна Добавление ссылки на службу: ГИПЕРССЫЛКИ «http://localhost:8000/ServiceModelSamples/Service» http://localhost:8000/ServiceModelSamples/Service и нажмите кнопку **Go** кнопки. Служба CalculatorService должна отображаться в списке служб. Дважды щелкните службу CalculatorService, чтобы развернуть список контрактов, реализованных службой. Оставьте пространство имен по умолчанию и нажмите **ОК** кнопки.  
  
     При добавлении ссылки на службу с помощью Visual Studio в обозревателе решений для проекта GettingStartedClient появится новый элемент в папке «Ссылки на службы».  Если вы используете [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство, будет создан файл исходного кода и файл app.config.  
  
     Можно также использовать программу командной строки [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с соответствующими параметрами для создания клиентского кода. В следующем примере создается файл кода и файл конфигурации для службы. В первом примере показано, как создать прокси на VB, а во втором то же самое, но с использованием C#:  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
 Мы создали прокси, который будет использовать клиентское приложение для вызова службы калькулятора. Перейти к следующему разделу ряда: [как: Настройка клиента](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## <a name="see-also"></a>См. также  
 [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)  
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
