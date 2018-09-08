---
title: Практическое руководство. Создание клиента Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 9e6d75bf8911a3c36e63b3bc108faae823434d1d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44221653"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Практическое руководство. Создание клиента Windows Communication Foundation

Это четвертая из шести шагов, необходимых для создания приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).

В этом разделе описывается, как получить метаданные из службы WCF и использовать его для создания прокси WCF, который можно получить доступ к службе. Эта задача выполняется с помощью функции добавления ссылки на службу, предоставляемой средой Visual Studio. Данное средство получает метаданные из конечной точки обмена метаданными службы и создает файл управляемого исходного кода для клиентского прокси на выбранном языке (по умолчанию на C#). Кроме создания прокси клиента данное средство также создает или обновляет файл конфигурации клиента, позволяющий клиентскому приложению подключаться к службе в одной из конечных точек.

> [!NOTE]
> Можно также использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания класса прокси и конфигурации, вместо использования Add Service Reference в Visual Studio.

> [!WARNING]
> При вызове службы WCF из проекта библиотеки классов в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] можно использовать функцию добавления ссылки на службу для автоматического создания прокси-сервера и связанный файл конфигурации.  Файл конфигурации не будет использоваться проектом библиотеки классов. Необходимо добавить параметры из созданного файла конфигурации в файл app.config, соответствующий исполняемому файлу, вызывающему библиотеку классов.

 Клиентское приложение использует созданный прокси-класс для взаимодействия со службой. Эта процедура описана в [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="to-create-a-windows-communication-foundation-client"></a>Создание клиента Windows Communication Foundation

1.  Создайте новый проект консольного приложения, щелкнув правой кнопкой решение Приступая к работе, выбрав **добавить**, **новый проект**. В диалоговом окне **Добавить новый проект** в левой части окна выберите **Windows** в разделе **C#** или **VB**. В центральной части диалогового окна выберите **Консольное приложение**. Задайте для проекта имя `GettingStartedClient`.

2.  Задать целевую платформу проекта gettingstartedclient версию .NET Framework 4.5, щелкнув правой кнопкой **GettingStartedClient** в обозревателе решений и выбрав **свойства**. В раскрывающемся списке **Требуемая версия .NET Framework** выберите значение **.NET Framework 4.5**. Задание целевой платформы для проекта Visual Basic немного отличается, в диалоговом окне свойств проекта GettingStartedClient, нажмите кнопку **компиляции** в левой части экрана, а затем щелкните **Дополнительно Параметры компиляции** кнопку в левом нижнем углу диалогового окна. Выберите пункт **.NET Framework 4.5** в раскрывающемся списке **Требуемая версия .NET Framework**.

     Задание целевой платформы приведет к Visual Studio 2011 к перезагрузке решения, нажмите клавишу **ОК** при появлении запроса.

3.  Добавьте ссылку на сборку System.ServiceModel для проекта GettingStartedClient, щелкнув правой кнопкой мыши **ссылку** папку проекта GettingStartedClient в обозревателе решений и выберите **добавить** Ссылка. В диалоговом окне **Добавить ссылку** выберите в левой части диалогового окна пункт **Платформа**. В текстовом поле «Поиск сборок» введите `System.ServiceModel`. В центральной части диалогового окна выберите **System.ServiceModel**, нажмите кнопку **Добавить**, а затем кнопку **Закрыть**. Сохраните решение, нажав кнопку **сохранить все** кнопку под главным меню.

4.  Далее вы добавите ссылку на службу для службы калькулятора. Прежде чем это можно будет сделать, следует запустить консольное приложение GettingStartedHost. После запуска размещения правой кнопкой мыши **ссылки** папку проекта GettingStartedClient в **обозревателе решений** и выберите **добавить**  >   **Службе Справочник по**. Введите следующий URL-адрес в поле "адрес" **Add Service Reference** диалоговое окно: [ http://localhost:8000/ServiceModelSamples/Service ](http://localhost:8000/ServiceModelSamples/Service) и нажмите кнопку **Go** кнопки. CalculatorService должна отображаться в списке служб. Дважды щелкните CalculatorService и он будет развернуть и Показать контрактов службы, реализованном в службе. Оставьте пространство имен по умолчанию и нажмите кнопку **ОК** кнопки.

     При добавлении ссылки на службу с помощью Visual Studio в обозревателе решений для проекта GettingStartedClient появится новый элемент в папке «Ссылки на службы».  Если вы используете [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средство, будет создан файл исходного кода и файл app.config.

     Можно также использовать средство командной строки [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с соответствующими параметрами, чтобы создать клиентский код. В следующем примере создается файл кода и файл конфигурации для службы. В первом примере показано, как создать прокси на VB, а во втором то же самое, но с использованием C#:

    ```
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service
    ```

    ```csharp
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service
    ```

 Мы создали прокси, который будет использовать клиентское приложение для вызова службы калькулятора. Перейти к следующей статье из серии: [как: Настройка клиента](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>См. также

- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
- [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
