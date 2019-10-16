---
title: Практическое руководство. Размещение службы WCF в управляемом приложении
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: e3adcad6ba70aa64b797325cd45a043301d7e680
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320980"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>Как разместить службу WCF в управляемом приложении

Для размещения службы внутри управляемого приложения внедрите код службы внутрь кода управляемого приложения, определите конечную точку для службы императивно в коде, декларативно с помощью конфигурации или посредством конечных точек по умолчанию, а затем создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.

Чтобы начать принимать сообщения, вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>. При этом создается и открывается прослушиватель для этой службы. Такое размещение службы часто называется "резидентным", так как управляемое приложение самостоятельно выполняет функции ведущего приложения. Чтобы закрыть службу, вызовите метод <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> для <xref:System.ServiceModel.ServiceHost>.

Служба может также размещаться в управляемой службе Windows, в службах IIS или в службе активации процесса Windows (WAS). Дополнительные сведения о параметрах размещения для службы см. в разделе [службы хостинга](hosting-services.md).

Размещение служб в управляемом приложении - самый гибкий вариант размещения, так как в этом случае требуется минимальное развертывание инфраструктуры. Дополнительные сведения о размещении служб в управляемых приложениях см. [в разделе Размещение в управляемом приложении](./feature-details/hosting-in-a-managed-application.md).

В следующей процедуре показано, как реализовать резидентную службу в консольном приложения.

## <a name="create-a-self-hosted-service"></a>Создание самостоятельно размещенной службы

1. Создайте новое консольное приложение:

   1. Откройте Visual Studio и выберите в меню **файл** пункт **создать** **проект**  > .

   2. В списке **Установленные шаблоны** выберите элемент **визуальный C#**  или **Visual Basic**, а затем выберите **Рабочий стол Windows**.

   3. Выберите шаблон **консольное приложение** . Введите `SelfHost` в поле **имя** и нажмите кнопку **ОК**.

2. Щелкните правой кнопкой мыши **резидент** в **Обозреватель решений** и выберите команду **Добавить ссылку**. Выберите **System. ServiceModel** на вкладке **.NET** и нажмите кнопку **ОК**.

    > [!TIP]
    > Если окно **Обозреватель решений** не отображается, выберите **Обозреватель решений** в меню **вид** .

3. Дважды щелкните **Program.CS** или **Module1. vb** в **Обозреватель решений** , чтобы открыть его в окне кода, если оно еще не открыто. Добавьте следующие инструкции в начало файла:

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. Определите и реализуйте контракт службы. В этом примере определяется служба `HelloWorldService`, которая возвращает сообщение на основании входных данных, передаваемых службе.

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > Дополнительные сведения об определении и реализации интерфейса службы см. [в разделе инструкции. определение контракта службы](how-to-define-a-wcf-service-contract.md) и [инструкции. Реализация контракта службы](how-to-implement-a-wcf-contract.md).

5. В начале метода `Main` создайте экземпляр класса <xref:System.Uri> с базовым адресом для службы.

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>, передав <xref:System.Type>, представляющий тип службы, и универсальный код ресурса (URI) базового адреса в метод <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>. Включите публикацию метаданных и вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> в <xref:System.ServiceModel.ServiceHost>, чтобы инициализировать службу и подготовить ее к приему сообщений.

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > В этом примере используются конечные точки по умолчанию, и для данной службы не требуется файл конфигурации. Если конечные точки не настроены, то среда выполнения создает одну конечную точку для каждого базового адреса в каждом контракте службы, реализованном в службе. Дополнительные сведения о конечных точках по умолчанию см. в разделе [упрощенная конфигурация](simplified-configuration.md) и [упрощенная конфигурация для служб WCF](./samples/simplified-configuration-for-wcf-services.md).

7. Нажмите клавиши **Ctrl**+**SHIFT**+**B** , чтобы создать решение.

## <a name="test-the-service"></a>Проверка службы

1. Нажмите клавиши **Ctrl**+**F5** , чтобы запустить службу.

2. Откройте **тестовый клиент WCF**.

    > [!TIP]
    > Чтобы открыть **тестовый клиент WCF**, откройте Командная строка разработчика для Visual Studio и выполните **клиент WcfTestClient. exe**.

3. Выберите **Добавить службу** в меню **файл** .

4. Введите `http://localhost:8080/hello` в поле адрес и нажмите кнопку **ОК**.

    > [!TIP]
    > Убедитесь, что служба запущена. В противном случае проверка дает отрицательный результат на этом этапе. Если базовый адрес в коде был изменен, используйте на этом этапе измененный базовый адрес.

5. Дважды щелкните элемент **sayHello** в узле **Мои проекты "Мои службы** ". Введите свое имя в столбец **значение** в списке **запрос** и нажмите кнопку **вызвать**.

   В списке **ответов** появится ответное сообщение.

## <a name="example"></a>Пример

В следующем примере создается объект <xref:System.ServiceModel.ServiceHost> для размещения службы типа `HelloWorldService`, затем вызывается метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>. Базовый адрес предоставляется в коде, включена публикация метаданных и используются конечные точки по умолчанию.

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>См. также

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [Практическое руководство. Размещение службы WCF в IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Резидентное размещение](./samples/self-host.md)
- [Размещение служб](hosting-services.md)
- [Практическое руководство. Определение контракта службы](how-to-define-a-wcf-service-contract.md)
- [Практическое руководство. Реализация контракта службы](how-to-implement-a-wcf-contract.md)
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Использование привязок для настройки служб и клиентов](using-bindings-to-configure-services-and-clients.md)
- [Привязки, предоставляемые системой](system-provided-bindings.md)
