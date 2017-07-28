---
title: "Как создать клиент Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "клиенты [WCF], выполнение"
  - "клиенты WCF [WCF], выполнение"
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
caps.latest.revision: 64
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 64
---
# Как создать клиент Windows Communication Foundation
Это четвертый из шести шагов, необходимый для создания простого приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].Общие сведения обо всех шести шагах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 В данном разделе описывается, как извлечь метаданные из службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] и использовать, чтобы создать прокси [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для доступа к службе.Эта задача выполняется с помощью функции добавления ссылки на службу, предоставляемой средой Visual Studio.Данное средство получает метаданные из конечной точки обмена метаданными службы и создает файл управляемого исходного кода для клиентского прокси на выбранном языке \(по умолчанию на C\#\).Кроме создания клиентского прокси, данное средство также создает или обновляет файл конфигурации клиента, позволяющий клиентскому приложению подключаться к службе в одной из конечных точек.  
  
> [!NOTE]
>  Для создания прокси\-класса и конфигурации также можно использовать средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) вместо добавления ссылки на службу в среде Visual Studio.  
  
> [!WARNING]
>  При вызове службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] из проекта библиотеки учетной записи\-посредника в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] можно использовать команду «Добавить ссылку на службу» для автоматического создания прокси и связанного файла конфигурации.Файл конфигурации не будет использоваться проектом библиотеки классов.Необходимо добавить параметры из созданного файла конфигурации в файл app.config, соответствующий исполняемому файлу, вызывающему библиотеку классов.  
  
 Клиентское приложение использует созданный прокси\-класс для взаимодействия со службой.Эта процедура описана в разделе [Практическое руководство. Использование клиента](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
### Создание клиента Windows Communication Foundation  
  
1.  Создайте новый проект консольного приложения, щелкнув правой кнопкой мыши решение «Приступая к работе» и последовательно выбрав **Добавить** и **Создать проект**.В диалоговом окне **Добавить новый проект** в левой части окна выберите **Windows** во вкладке **C\#** или **VB**.В центральной части диалогового окна выберите **Консольное приложение**.Задайте имя проекта — `GettingStartedClient`.  
  
2.  Выберите для GettingStartedClient требуемую версию .NET Framework — .NET Framework 4.5, щелкнув правой кнопкой мыши **GettingStartedClient** в обозревателе решений и выбрав **Свойства**.В раскрывающемся списке **Требуемая версия .NET Framework** выберите значение **.NET Framework 4.5**.Выбор требуемой версии .NET Framework для проекта Visual Basic несколько отличается от варианта, приведенного выше. В диалоговом окне «Свойства» проекта, GettingStartedClient перейдите на вкладку в левой части экрана **Компиляция** и нажмите кнопку **Дополнительные параметры компиляции** в нижнем левом углу диалогового окна.Выберите пункт **.NET Framework 4.5** в раскрывающемся списке **Требуемая версия .Net Framework**.  
  
     Указание требуемой версии .NET Framework приведет к перезагрузке решения в среде Visual Studio 2011. Нажмите кнопку **ОК**, когда появится соответствующий запрос.  
  
3.  Добавьте в проект GettingStartedClient ссылку на сборку System.ServiceModel. Для этого в обозревателе решений щелкните правой кнопкой мыши папку **Ссылка** проекта GettingStartedClient и выберите пункт **Добавить** ссылку.В диалоговом окне **Добавить ссылку** выберите в левой стороне диалогового окна пункт **Платформа**.В текстовом поле «Поиск сборок» введите `System.ServiceModel`.В центральной части диалогового окна выберите **System.ServiceModel**, нажмите кнопку **Добавить**, а затем кнопку **Закрыть**.Сохраните решение, нажав кнопку **Сохранить все** в главном меню.  
  
4.  Затем необходимо добавить ссылку на службу калькулятора.Прежде чем это можно будет сделать, следует запустить консольное приложение GettingStartedHost.После запуска основного приложения в обозревателе решений нужно щелкнуть правой кнопкой мыши папку «Ссылки» проекта GettingStartedClient, выбрать пункт «Добавить ссылку на службу» и ввести в поле адреса следующий URL\-адрес: http:\/\/localhost:8000\/ServiceModelSamples\/Service. Затем следует нажать кнопку **Перейти**.Служба CalculatorService должна отображаться в списке служб. Дважды щелкните службу CalculatorService, чтобы развернуть список контрактов, реализованных службой.Оставьте пространство имен по умолчанию и нажмите кнопку **ОК**.  
  
     При добавлении ссылки на службу с помощью Visual Studio в обозревателе решений для проекта GettingStartedClient появится новый элемент в папке «Ссылки на службы».При использовании средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) создаются файл исходного кода и файл app.config.  
  
     Чтобы создать клиентский код, также можно использовать программу командной строки [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с соответствующими параметрами.В следующем примере создается файл кода и файл конфигурации для службы.В первом примере показано, как создать прокси на VB, а во втором то же самое, но с использованием C\#:  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
 Мы создали прокси, который будет использовать клиентское приложение для вызова службы калькулятора.Перейти к следующему разделу обучающего урока [Практическое руководство. Настройка клиента](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## См. также  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)   
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Как использовать Svcutil.exe для загрузки документов метаданных](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)