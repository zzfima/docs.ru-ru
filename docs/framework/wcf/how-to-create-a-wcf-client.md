---
title: Практическое руководство. Создание клиента Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 9572f3e2c0cddf75daf343f250b16e94bc2b0dbf
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181674"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Практическое руководство. Создание клиента Windows Communication Foundation

Это четвертая из шести шагов, необходимых для создания приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).

В этом разделе описывается, как получить метаданные из службы WCF и использовать его для создания прокси WCF, который можно получить доступ к службе. Эта задача выполняется с помощью **Add Service Reference** функциональных возможностях, предоставляемых Visual Studio. Данное средство получает метаданные из конечной точки обмена метаданными службы и создает файл управляемого исходного кода для клиентского прокси на выбранном языке (по умолчанию на C#). Кроме создания прокси клиента данное средство также создает или обновляет файл конфигурации клиента, позволяющий клиентскому приложению подключаться к службе в одной из конечных точек.

> [!NOTE]
> Можно также использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания класса прокси и конфигурации, вместо использования **Add Service Reference** в Visual Studio.

> [!NOTE]
> При вызове службы WCF из проекта библиотеки классов в Visual Studio, можно использовать **Add Service Reference** компонентов для автоматического создания прокси-сервера и связанный файл конфигурации. Файл конфигурации не будет использоваться проектом библиотеки классов. Необходимо добавить параметры в созданный файл конфигурации в файл app.config для исполняемого файла, который вызывает библиотеку классов.

Клиентское приложение использует созданный прокси-класс для взаимодействия со службой. Эта процедура описана в [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="to-create-a-windows-communication-foundation-client"></a>Создание клиента Windows Communication Foundation

1. Создайте новый проект консольного приложения в Visual Studio. Щелкните правой кнопкой мыши на решение Приступая к работе в **обозревателе решений** и выберите **добавить** > **новый проект**. В **Добавление нового проекта** диалоговое окно, в левой части окна выберите **Windows Desktop** категорию **Visual C#** или **Visual Basic**. Выберите **консольное приложение (.NET Framework)** шаблона и назовите проект **GettingStartedClient**.

2. Добавьте ссылку на сборку System.ServiceModel для проекта GettingStartedClient. Щелкните правой кнопкой мыши **ссылки** папку проекта GettingStartedClient в **обозревателе решений**, а затем выберите **добавить ссылку**. В **добавить ссылку** диалоговом окне выберите **Framework** в левой части диалогового окна в разделе **сборки**. Найдите и выберите **System.ServiceModel**, а затем выберите **ОК**. Сохраните решение, выбрав **файл** > **сохранить все**.

3. Добавьте ссылку на службу для службы калькулятора.

   1. Сначала запустите консольное приложение GettingStartedHost.

   2. После запуска размещения правой кнопкой мыши **ссылки** папку проекта GettingStartedClient в **обозревателе решений** и выберите **добавить**  >   **Службе Справочник по**.

   3. Введите следующий URL-адрес в поле "адрес" **Add Service Reference** диалоговое окно: [http://localhost:8000/GettingStarted/CalculatorService](http://localhost:8000/GettingStarted/CalculatorService)

   4. Выберите **Go**.

   CalculatorService отображается в **служб** поле со списком. Дважды щелкните CalculatorService, чтобы развернуть его и Показать контрактов службы, реализованном в службе. Оставьте пространство имен по умолчанию как- и выбрать **ОК**.

    При добавлении ссылки на службу, с помощью Visual Studio, новый элемент появляется в **обозревателе решений** под **ссылок на службы** папку проекта GettingStartedClient. Если вы используете [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) создаются средство, файл исходного кода и файл app.config.

    Можно также использовать средство командной строки [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с соответствующими параметрами, чтобы создать клиентский код. В следующем примере создается файл кода и файл конфигурации для службы. Первый пример показано, как создать прокси на VB, и второй показано, как создать прокси на языке C#:

    ```shell
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
    ```

    ```shell
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
    ```

## <a name="next-steps"></a>Следующие шаги

Вы создали прокси, который клиентское приложение будет использовать для вызова службы калькулятора. Перейдите к следующему разделу в ряду.

> [!div class="nextstepaction"]
> [Практическое руководство. Настройка клиента](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>См. также

- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
- [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
